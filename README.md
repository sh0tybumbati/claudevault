# claudevault

Persistent knowledge base for any Claude instance working with **sh0tybumbati** (advpratt@gmail.com).

Pull this repo at the start of any session on any machine. It contains everything needed to pick up exactly where we left off — no re-explaining projects, preferences, or history.

---

## How to use this

```bash
# At start of new session on any machine
git clone https://github.com/sh0tybumbati/claudevault
cat claudevault/README.md         # you are here
cat claudevault/INCOME.md         # current money status
cat claudevault/ENVIRONMENT.md    # machine setup
cat claudevault/projects/*.md     # specific project detail
```

**Keep this up to date.** At the end of any significant session, push new findings here.

---

## Who is the user

- **GitHub / Thingiverse / Itch.io**: `sh0tybumbati`
- **Email**: advpratt@gmail.com
- **Render account**: advpratt@gmail.com
- **Platform**: Android (Termux) — primary dev machine
- **Background**: Game developer, business intelligence, mechanical engineering, 3D printing

## How to work with them

- Direct and concise — no filler, no preamble
- They give broad latitude ("do whatever you want") — be opinionated, make decisions, execute
- They'll course-correct if something's wrong — don't ask permission for every step
- Babystep them through UI tasks (Itch.io, Stripe dashboard) — they handle the clicks, Claude handles everything else
- Don't add features beyond what's asked
- Don't summarize what you just did — they can read the diff

## Quick-reference: standing behaviors

- After any meaningful code change: update CHANGELOG, README, FEATURES.md, PLANNING.md (use `update-docs` skill)
- Silicon Tycoon live-server: always port 3000, never 8080
- YieldDesk is not a product — never add monetization, paywalls, or Pro tiers

---

## Contents

| File | What's in it |
|---|---|
| `INCOME.md` | Every income stream, status, what's live |
| `ENVIRONMENT.md` | Machine setup, tools, accounts, API keys status |
| `PREFERENCES.md` | How to work with the user, standing behaviors |
| `RESOURCES.md` | Useful references — APIs, tools, links |
| `projects/silicon-tycoon.md` | Full Silicon Tycoon project knowledge |
| `projects/yield-desk.md` | YieldDesk — semiconductor calculator SaaS |
| `projects/feature-creep.md` | Feature Creep — deck-building game |
| `projects/ralph.md` | Ralph — autonomous Claude Code loop |
| `projects/anglish-wordhoard.md` | Anglish Word-hoard dictionary app |
| `projects/space-game.md` | Space Game — Phaser 3 prototype |
| `projects/trivium.md` | Trivium — trivia hosting system (~90%, deployed) |
| `projects/okibar.md` | Okibar — karaoke bar management (80%+, deployed) |
| `projects/dubs-mods.md` | Rimworld mods (dubs-heatpump, etc.) |
| `projects/bom-tracker.md` | BOM Tracker — hardware bill of materials, Amazon/Lazada/AliExpress |
| `projects/budget.md` | Budget tracker — full-stack, Docker-ready |
| `projects/fps-arena.md` | FPS Arena — Godot 4, singleplayer only so far |
| `projects/arduarm.md` | ArduArm — Raspberry Pi pan/tilt security camera |
| `projects/voidspace.md` | Voidspace — Reddit alternative, schema only |
