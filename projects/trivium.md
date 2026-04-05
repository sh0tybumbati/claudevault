# Trivium

**GitHub**: https://github.com/sh0tybumbati/trivium
**Local**: `~/projects/trivium/`
**State**: ~90% MVP
**Stack**: React 18, TypeScript, Vite, Tailwind CSS, Node.js, Express, WebSocket (ws), SQLite3
**Deployed**: Render
- Build: `npm run build` from project root, then `cd server && npm start`
- Dev: `npm run dev` (frontend) + `cd server && npm run dev` (backend)
- Port: 3001

## What it is
Professional networked trivia hosting system. A controller drives gameplay that syncs in real-time to any number of browser-connected devices — projector screens, player phones, tablets. Questions stored in SQLite with import/export.

## Features built
- Real-time multi-device WebSocket sync (zero-latency)
- Host / Big Screen (projector) / Guest (player) modes
- SQLite question database with full CRUD + image support + import/export
- Art Deco professional UI
- Player mode: join via QR code, real-time scoring
- Multiple choice + write-in question types
- Leaderboard (host-toggled, shows top 10)
- Auto-scoring on answer reveal for multiple choice
- Manual point awarding for write-in (host panel)
- Awarded answers displayed on Big Screen when answer revealed (fixed 2026-04-04)
- Open Trivia DB import — pick category, difficulty, amount (1–50), appends to question bank
- Category filtering, question limits, timed rounds

## Planned: Danger Mode (Jeopardy knockoff)
Jeopardy-style board — categories as columns, point tiers as rows. Players buzz in, wrong answers penalize.

**DB gap to fix first**: no `point_value` or `difficulty` column on questions. Need to:
1. Add `point_value` int column (default 200) via DB migration
2. Update question form + OTDB import to set it (OTDB has difficulty → easy=200, medium=400, hard=600)
3. Build Danger game mode: board view, buzz-in via player devices, +/- scoring

## Known remaining gaps
- Danger mode — needs `point_value` DB column first (designed, not built)
- Team mode (grouped scoring) — not started
- Admin dashboard for multi-game management — not started

## Market
- Bars and restaurants running trivia nights
- Corporate team-building event organizers
- Trivia leagues and quiz masters
- **Pricing**: $50–300/month per venue as SaaS

## Productization path
1. ~~Add scoring + leaderboard~~ — done
2. ~~Open Trivia DB import~~ — done
3. Danger mode (Jeopardy knockoff) — needs point_value column
4. Team modes
5. Polish + launch on ProductHunt targeting bar owners
