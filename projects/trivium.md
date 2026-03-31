# Trivium

**GitHub**: https://github.com/sh0tybumbati/trivium
**State**: 85–90% complete (updated 2026-03-31 — active development, last commit today)
**Stack**: React 18, TypeScript, Vite, Tailwind CSS, Node.js, Express, WebSocket (ws), SQLite3, QR codes
**Deployed**: Render

## What it is
Professional networked trivia hosting system. A controller drives gameplay that syncs in real-time to any number of browser-connected devices — projector screens, player phones, tablets. Questions stored in SQLite with import/export.

## Features built
- Real-time multi-device WebSocket sync (zero-latency)
- Host view / Big Screen (projector) / Player mode — all three implemented
- Multiple choice + write-in questions with point-based scoring
- SQLite question database with full CRUD + image support + import/export
- QR code player join
- Art Deco professional UI / theme system
- Deployed to Render

## Missing (to reach MVP)
- Team modes
- Final polish on feud/reveal mechanics (active fixes as of 2026-03-31)

## Market
- Bars and restaurants running trivia nights
- Corporate team-building event organizers
- Trivia leagues and quiz masters
- **Pricing**: $50–300/month per venue as SaaS

## Productization path
1. Add scoring + team modes (~1 week)
2. Add admin dashboard (~1 week)
3. Package as Docker container for easy self-hosting
4. OR: host as multi-tenant SaaS (one instance per venue subdomain)
5. Launch on ProductHunt targeting bar owners
