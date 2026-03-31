# Income Streams

Last updated: 2026-03-31

## Status overview

| Product | Platform | Price | Status | Monthly potential |
|---|---|---|---|---|
| Silicon Tycoon | Itch.io | $3.99 | 🟡 Ready — pending publish | Passive |
| Feature Creep | Itch.io | PWYW $2 | 🟡 Ready — pending publish | Passive |
| YieldDesk Free | yielddesk-4lo5.onrender.com | Free | 🟢 Live | — |
| YieldDesk Pro | Same | $9/mo | 🔴 Stripe not connected | $100–$1,800/mo |
| STL packs | Cults3D | $2–5 | 🔴 Not started | Passive |
| Dubs mods Ko-fi | Ko-fi | Tips | 🔴 Not set up | Small passive |

---

## YieldDesk

**Live at**: https://yielddesk-4lo5.onrender.com
**GitHub**: https://github.com/sh0tybumbati/yielddesk
**Render service ID**: `srv-d74v20haae7s73bo6rv0`

### What's built
- Murphy, Poisson, Rectangular, Moore, Seeds, Bose-Einstein yield models
- 26 process nodes (3μm → 14A Intel) with ITRS D₀ data
- Process maturity: Pilot (3×) / Ramp (2×) / HVM (1×) / Mature (0.7×)
- Wafer cost + mask cost + reticle utilization
- Amortized mask cost per die by wafer volume
- Yield sensitivity curve (unique — no other tool has this)
- URL permalink sharing
- Scribe lines, critical area, edge exclusion
- Live wafer map canvas

### What's NOT built yet
- Stripe payment flow (backend code exists in `api/server.js`, needs keys)
- Pro features hidden (CSV export, Poisson comparison, API access)
- Node comparison table (same die, multiple nodes side-by-side)
- Custom domain (using onrender.com for now)

### To go live with Pro
1. User creates Stripe account
2. User creates a $9/mo recurring price product in Stripe
3. Provide to Claude: `STRIPE_SECRET_KEY`, `STRIPE_WEBHOOK_SECRET`, `STRIPE_PRICE_ID`
4. Claude sets env vars on Render via API and re-enables Pro UI
5. Done — payments live

### Differentiation vs SemiAnalysis (main competitor)
| Feature | SemiAnalysis | YieldDesk |
|---|---|---|
| Process node library with D₀ | — | ✓ |
| Process maturity scaling | — | ✓ |
| Intel Angstrom nodes | — | ✓ |
| Wafer + mask cost database | — | ✓ |
| Mask cost amortization | — | ✓ |
| Reticle utilization | — | ✓ |
| Yield sensitivity curve | — | ✓ (unique) |
| URL sharing | — | ✓ |
| 7 yield models | ✓ | 6 |
| Panel support | ✓ | — |
| Reticle shot map | ✓ | — |

---

## Silicon Tycoon

**Local**: `~/projects/silicon-tycoon/`
**GitHub**: https://github.com/sh0tybumbati/silicon-tycoon
**Itch.io zip**: `~/projects/silicon-tycoon-itchio.zip` (15MB, clean)
**Itch.io copy**: `~/projects/silicon-tycoon/ITCHIO_PAGE.md`

### State
- v0.22.0 Early Access
- Version strings fixed (was stuck at v0.18.0)
- Disabled menu buttons removed, replaced with "How to Play" modal
- Full gameplay loop working: Design → Tape-Out → Contract → Bin → Package → Market → Finance
- 4 business models: Fabless, Foundry, IP Licensor, IDM
- 5 eras: 1971, 1980, 1990, 2000, 2010

### To publish on Itch.io
1. Go to itch.io/game/new
2. Title: "Silicon Tycoon — Early Access"
3. Kind: HTML (browser game)
4. Upload silicon-tycoon-itchio.zip, tick "play in browser"
5. Price: $3.99 minimum
6. Paste description from ITCHIO_PAGE.md
7. Tags: strategy, simulation, tycoon, management, business, browser, historical
8. Publish

### Known gaps (post-launch fixes)
- No win condition (open sandbox)
- No save slots (auto-saves to localStorage)
- No audio
- Balance not tuned for all difficulties

---

## Feature Creep

**GitHub**: https://github.com/sh0tybumbati/feature-creep
**Local**: `~/projects/feature-creep/`
**Itch.io zip**: `~/projects/feature-creep-itchio.zip` (165KB, clean)
**Live demo**: https://sh0tybumbati.github.io/feature-creep/

### State
- 90% complete — game jam entry, fully playable
- Deck-building game satirizing game development / scope creep
- Has promo art: `~/projects/feature-creep/promoart.png`
- Built with React + TypeScript + Vite (pre-built, no build step needed)

### To publish on Itch.io
1. itch.io/game/new
2. Title: "Feature Creep"
3. Kind: HTML
4. Upload feature-creep-itchio.zip, tick "play in browser"
5. Price: Pay What You Want, suggested $2
6. Short description: "A satirical deck-building game about managing a game dev project without letting scope creep kill it."
7. Tags: card-game, deck-building, strategy, game-jam, browser, funny
8. Publish

---

## STL Packs (not started)

User's Thingiverse designs:
- V Roller from 608 Bearings
- Parametric Spool Holder (75 & 90mm)
- Heatbed to Glassplate adapter

**Path to income**: Upload to Cults3D as paid STL packs ($2–5 each).
Cults3D takes 30% cut. No setup cost.
Best approach: bundle related designs into themed packs.

---

## Trivium (future SaaS)

**GitHub**: https://github.com/sh0tybumbati/trivium
**State**: 70% complete
**What it is**: Professional trivia hosting system — WebSocket sync, Art Deco UI, multi-device, SQLite questions
**Market**: Bars and venues running pub trivia — would pay $50–300/month
**Missing**: Player scoring, team modes, admin dashboard
**Stack**: Node.js, WebSocket, SQLite

---

## Okibar (future SaaS)

**GitHub**: https://github.com/sh0tybumbati/Okibar
**State**: 30% complete
**What it is**: Karaoke bar management — YouTube song integration, Socket.io queue sync, singer management, public display view
**Market**: Every karaoke bar globally — replaces expensive POS systems
**Missing**: Most features — needs significant work
**Stack**: Node.js, Socket.io, YouTube API
