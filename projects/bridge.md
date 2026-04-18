# Bridge

**Status**: Design complete, not yet started (as of 2026-04-19)
**Doc**: `/sdcard/Download/bridge-design-doc.md`

## What it is

Private, offline-first relationship maintenance app. Helps users have more meaningful conversations with people they care about. Not a social network — no social graph, no sharing. Think personal journal, not CRM.

Core insight: relationship drift happens from neglect, not conflict — and neglect happens because people don't know how to re-initiate or go deeper.

## Stack

| Layer | Choice |
|---|---|
| Frontend | React + Vite |
| Mobile wrapper | Capacitor (preferred over React Native) |
| Styling | Tailwind CSS |
| State | Zustand |
| Local DB | SQLite via Capacitor SQLite plugin |
| Cloud sync (optional) | Supabase (Postgres + Auth) |
| Notifications | Capacitor Local Notifications (no server needed) |
| AI | Anthropic API — `claude-sonnet-4-20250514` |

## Routes

```
/                        → Dashboard (today view + nudges)
/people                  → People list
/people/:id              → Person profile
/people/:id/starters     → AI conversation starters
/people/:id/practice     → Conversation practice
/people/new              → Add person
/templates               → Check-in templates library
/settings                → Settings, sync, notifications
```

## Data model (SQLite)

- **people** — name, relationship_type, avatar, notes, last_contacted, contact_frequency_goal
- **tags** + **person_tags** — custom labels (college, work, close, etc.)
- **life_events** — per-person; event_text, date_added, follow_up_date, resolved
- **saved_starters** — favorited AI-generated starters per person
- **practice_drafts** — saved conversation practice drafts
- **contact_log** — optional manual contact history

## Key features

### AI conversation starters (core feature)
User taps "Get conversation ideas" on a person profile → app bundles relationship type + recent life events + last contact date + notes (opt-in) → Anthropic API → returns 3–5 specific, contextual openers. Refresh, save favorites, or copy to clipboard.

API payload shape:
```json
{
  "relationship": "close friend",
  "last_contact_days_ago": 45,
  "recent_events": ["started new job", "moved to new apartment"],
  "tone_preference": "casual and warm"
}
```
Returns: `{ "starters": ["...", "..."] }`

### Conversation practice mode
For difficult conversations user is avoiding. Select type (apologize / set boundary / share difficult news / ask for something / mental health check-in / reconnecting). Optionally describe situation. AI generates 2–3 approaches with different tones (direct / gentle / humor-first). One-shot generation + refinement — NOT a chatbot.

### Check-in templates ("How Are You Really")
Static JSON curated content. Categories: general depth, after a hard time, celebration, long time no talk, mental health check-in. 3–5 questions each. No AI needed.

### Nudges & reminders
Triggers: user-set frequency, life event follow-up dates, lapsed contact detection.
Rules: max 1 nudge/person/week, snooze options, explicit opt-in only, quiet hours respected.

## Design tokens

- Background: warm off-white `#FAF7F2` / dark mode: `#1E1A17`
- Accent: terracotta `#C4714A` or sage green `#7A9E7E`
- Typography: humanist serif headings (Lora/Playfair), clean sans body (DM Sans)
- Rounded corners, generous padding, soft shadows — journal feel, not dashboard

## AI privacy rules

- User must explicitly opt in before notes are sent
- All API calls are one-shot — no conversation history stored server-side
- For production mobile: API key must be proxied server-side (never in client bundle)
- Dev/MVP: user-supplied key stored in device settings is acceptable

## MVP scope (Phase 1)

- [ ] Add/edit/delete people
- [ ] Add life events to a person
- [ ] Manual last-contacted tracking
- [ ] AI conversation starters (user-supplied API key)
- [ ] Basic local notifications for reminders
- [ ] SQLite local storage
- [ ] Responsive web UI (mobile-first)

## Deferred to Phase 2

- Conversation practice mode
- Check-in templates library
- Cloud sync (Supabase)
- Contact log history
- Tag filtering
- Dark mode

## Open questions (unresolved)

1. API key handling — user-supplied in device settings for MVP, or proxy backend from day one?
2. Sync — offline SQLite only for v1, or cross-device from the start?
3. Web PWA notifications — needs service worker; include in v1 or mobile-only first?
4. Avatar system — emoji + color placeholder (fast) or photo support (complex)?

## Folder structure

```
bridge/
├── src/
│   ├── components/people/ starters/ practice/ ui/
│   ├── pages/
│   ├── stores/        ← Zustand
│   ├── db/            ← SQLite queries
│   ├── api/           ← Anthropic API calls
│   ├── data/          ← static JSON templates
│   └── utils/
├── capacitor.config.ts
├── vite.config.ts
└── package.json
```

## Env vars

```
VITE_ANTHROPIC_API_KEY=
VITE_SUPABASE_URL=        (optional)
VITE_SUPABASE_ANON_KEY=   (optional)
```
