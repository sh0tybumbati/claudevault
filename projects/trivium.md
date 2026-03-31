# Trivium

**GitHub**: https://github.com/sh0tybumbati/trivium
**State**: 70% complete
**Stack**: Node.js, WebSocket, SQLite

## What it is
Professional networked trivia hosting system. A controller drives gameplay that syncs in real-time to any number of browser-connected devices — projector screens, player phones, tablets. Questions stored in SQLite with import/export.

## Features built
- Real-time multi-device WebSocket sync
- Controller view (host) / display view (projector) separation
- SQLite question database with import/export
- Art Deco professional UI
- Zero-latency sync

## Missing (to reach MVP)
- Player scoring and leaderboard
- Team modes
- Admin dashboard
- Question editor UI

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
