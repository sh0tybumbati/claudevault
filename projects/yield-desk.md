# YieldDesk

**Local**: `~/projects/yield-desk/`
**GitHub**: https://github.com/sh0tybumbati/yielddesk
**Live**: https://yielddesk-4lo5.onrender.com
**Render service ID**: `srv-d74v20haae7s73bo6rv0`
**Stack**: Vanilla JS (ES modules, no build), Node.js + Express backend, Stripe (pending)

## What it is
Semiconductor yield and wafer cost calculator. Distinct from SemiAnalysis (main competitor) by including a process node library, maturity modeling, Intel Angstrom nodes, and mask cost amortization — things engineers need but have to look up manually elsewhere.

## File structure
```
yield-desk/
  index.html          — full UI, no build step
  css/style.css       — dark theme, all styles
  js/calculator.js    — pure math (yield models, DPW, cost)
  js/app.js           — UI wiring, canvas drawing, URL sharing
  api/server.js       — Express: Stripe checkout, webhook, Pro API
  package.json        — dependencies: express, stripe
  .env.example        — env vars needed for production
```

## Features built

### Calculator (calculator.js)
- **6 yield models**: Murphy's Law, Poisson, Rectangular, Moore, Seeds, Bose-Einstein
- **26 process nodes**: 3μm (1971) → 14A Intel (2026), grouped Industry / Intel
- **Process maturity**: Pilot 3×D₀, Ramp 2×D₀, HVM 1×D₀, Mature 0.7×D₀
- **Dies per wafer**: Neter-Scheraga formula with scribe line pitch
- **Critical area**: separate from full die area, affects yield calc
- **Wafer costs**: node-specific market estimates ($500 → $28k)
- **Mask set costs**: node-specific ($75k at 3μm → $80M at 14A Intel)
- **Mask amortization**: spread across wafer volume
- **Reticle info**: utilization %, exceeds-field detection (26×33mm)
- **Sensitivity curve data**: yield vs die area at fixed node/maturity

### UI (app.js / index.html)
- Wafer map canvas — seeded RNG, scribe-line-aware tiling, heatmap fallback for tiny dies
- Yield sensitivity curve — plots all 80 points, marks current die position (unique feature)
- Cost breakdown panel: wafer cost/die + mask cost/die = total cost/die
- Reticle warning when die approaches or exceeds 26×33mm field
- Process node notes for Intel/special nodes
- URL permalink sharing (all params encoded in query string)
- Load from URL on page init

### Backend (api/server.js)
- `GET /checkout` → Stripe Checkout session redirect
- `POST /api/webhook` → handles subscription events (activate/deactivate Pro)
- `GET /api/v1/yield` → Pro API endpoint (key auth)
- `GET /api/v1/account` → lookup API key by session ID
- In-memory user store (replace with DB before scaling)

## Env vars needed (Render)
```
STRIPE_SECRET_KEY=sk_live_...
STRIPE_WEBHOOK_SECRET=whsec_...
STRIPE_PRICE_ID=price_...
BASE_URL=https://yielddesk-4lo5.onrender.com
PORT=3000
```

## Pro features (currently hidden, re-enable after Stripe)
- CSV export
- Murphy vs Poisson comparison
- Batch wafer calculator
- REST API access (1000 req/mo)
- Custom D₀ override

## To activate Stripe
1. User creates Stripe account, creates $9/mo recurring price
2. Share: STRIPE_SECRET_KEY, STRIPE_WEBHOOK_SECRET, STRIPE_PRICE_ID
3. Claude sets env vars via Render API:
   ```bash
   curl -X PATCH https://api.render.com/v1/services/srv-d74v20haae7s73bo6rv0/env-vars \
     -H "Authorization: Bearer rnd_FyVJ9jsHE11HhsaA2JpYStDsdKGo" \
     -H "Content-Type: application/json" \
     -d '[{"key":"STRIPE_SECRET_KEY","value":"sk_live_..."},...]'
   ```
4. Stripe webhook: point to `https://yielddesk-4lo5.onrender.com/api/webhook`
5. Re-enable Pro UI in index.html and app.js

## What to build next
- **Node comparison table** — same die, all nodes side-by-side (yield + cost/die)
- **SEO**: sitemap.xml, robots.txt
- **Patreon/Ko-fi link** for now until Stripe ready
