# Silicon Tycoon

**Local**: `~/projects/silicon-tycoon/`
**GitHub**: https://github.com/sh0tybumbati/silicon-tycoon
**Version**: v0.22.0 Early Access
**Stack**: Vanilla JS (ES modules), PixiJS 7.3.2, CSS themes, localStorage
**Entry point**: `index.html` — no build step, open directly or via live-server
**Live-server**: `cd ~/projects/silicon-tycoon && live-server --port=3000` (NEVER port 8080)

## What it is
Realistic semiconductor design and manufacturing tycoon game. Browser-based. Players design custom silicon dies, book foundry contracts, manage wafer yield, package chips, and build a chip company from 1971 to 2023+.

## Business models (4)
- **Fabless** — design only, contract out manufacturing (easiest start)
- **Foundry** — manufacture for others
- **IP Licensor** — design and license IP
- **IDM (Integrated Device Manufacturer)** — do everything

## Eras (5)
1971, 1980, 1990, 2000, 2010 — each locks available process nodes and capital

## Key screens and files

| Screen | HTML file | Main JS |
|---|---|---|
| Main menu | `index.html` | `js/main.js` |
| Die designer | `architecture.html` | `js/architecture.js`, `js/dieDesigner.js` |
| Wafer planner | `wafer.html` | `js/waferPlanner.js` |
| Foundry contracts | `contracts.html` | `js/contractsMain.js` |
| Die binning | `binning.html` | `js/binningMain.js` |
| Packaging | `packaging.html` | `js/packagingMain.js` |
| Market | `market.html` | `js/marketMain.js` |
| Finance | `finance.html` | `js/financeMain.js` |
| R&D | `rd.html` | `js/rdMain.js` |
| Company | `company.html` | `js/companyMain.js` |
| Player foundry | `foundry.html` | `js/foundryMain.js` |
| IP Portfolio | `ip-portfolio.html` | `js/ipPortfolioMain.js` |
| IP Marketplace | `ip-marketplace.html` | `js/ipMarketMain.js` |
| News | `news.html` | `js/newsMain.js` |

## Key library files

| File | Purpose |
|---|---|
| `js/dieDesigner.js` | PixiJS canvas engine — components, drag, resize, selection |
| `js/dieLibrary.js` | `COMPONENT_TYPES` definitions |
| `js/physics.js` | Performance/power/yield math |
| `js/gameState.js` | Shared game state, persistence |
| `js/marketEngine.js` | Silicon cycle, competitor pricing |
| `js/aiCompetitors.js` | 4 AI rivals — health, dynamic pricing, bankruptcy, market events |
| `js/narrativeEvents.js` + `js/narrativeNotifier.js` | 27 historical milestones with market impact |
| `js/newsLog.js` + `js/newsMain.js` | Persistent news feed, 6 categories, unread badge |
| `js/rdEngine.js` | 30-tech R&D tree — process nodes, architecture unlocks, manufacturing bonuses |
| `js/financeManager.js` | Loans, investors, IPO, valuation |

## Themes (4)
CSS variables via `--teal-primary`, `--magenta-primary`, etc.
- `vanilla` (Modern)
- `deco` (CyberDeco)
- `retro` (TVA / 70s)
- `apple2` (Green terminal)

## Die Designer specifics
- **Multi-select**: `multiSelectMode` flag on `DieDesigner`; `⊞` button toggles; shift+click on desktop
- **Drag**: `componentDragStart.components[]` stores start positions; `updateComponentDrag` moves all together
- **Resize handles**: `resizeHandlesContainer` (separate PIXI container); call `showResizeHandles()` after every `render(true)` during drag
- **Tools**: select, multiselect, pan, draw, copy, delete

## DEV console helpers (all pages)
```javascript
DEV.help()              // list all helpers
DEV.inspect()           // dump game state
DEV.tapAllDies()        // tape out all dies in current design
DEV.advanceWeeks(n)     // skip forward n weeks
DEV.completeContracts() // complete all active contracts instantly
DEV.listAllProducts()   // list all packaged products
```

## Ralph integration
- `.ralph/` directory configured in project root
- `.ralphrc` present
- Run: `cd ~/projects/silicon-tycoon && ~/.local/bin/ralph --live`

## Current state (as of 2026-03-31, post 42-commit pull)
- v0.22.0 [Unreleased] — CHANGELOG header not yet bumped to Released
- **~65–70% complete** — has a cohesive full gameplay loop, ready for Early Access launch
- Itch.io zip may be stale (needs rebuild after 42-commit pull)
- Itch.io copy written: `ITCHIO_PAGE.md`
- **Pending**: rebuild Itch.io zip, then user publishes on Itch.io at $3.99

## What was added in the 42-commit pull (Phases 16a–18)
- **Living AI Competitors**: 4 rivals (Nexatron, Spectra Semi, Vertex Graphics, Memorex) with health system, dynamic pricing, bankruptcy, market events
- **Narrative Events**: 27 scripted historical milestones (Intel 4004 → ChatGPT → CHIPS Act) with market impact and full-screen modals
- **News Feed**: `news.html` — persistent filterable log of all game events, unread badge, 6 categories
- **R&D Tech Tree**: 30 techs across process nodes (3μm→3nm), architecture unlocks (GPU/NPU/IO), manufacturing bonuses; weekly budget system; gates die types and process nodes

## Phase completion
| Phases | Status |
|---|---|
| Die designer, wafer, foundry, binning, packaging, market, finance, IP, company | ✅ Complete |
| Living AI competitors, narrative events, news feed, R&D | ✅ Complete (new) |
| Custom component design (Phase 9), ISA/IPC (10), memory chips (11), board-level (12), MCU (14), system integration (16) | ❌ Not started |

## Known gaps
- No win condition (open sandbox)
- No save slots (auto-save to localStorage only)
- No audio
- BORROWED TIME difficulty balance untested
- Competitor R&D, player-choice moments in narrative events — deferred
- Staffing, secondary share offerings — deferred
- Exclusive IP licensing negotiation UI — incomplete

## Gameplay loop
```
New Game → Design Die (Architecture) → Tape Out
→ Plan Wafer (Wafer) → Book Foundry (Contracts) → Wait weeks
→ Test Dies (Binning) → Package (Packaging)
→ List on Market → Advance Week → Collect Revenue
→ Manage Finance → Research (R&D) → Repeat
```
