---
name: BOM Tracker
---

# BOM Tracker

**Local**: `~/projects/bom-tracker/`
**Stack**: Vanilla JS, no build step, localStorage
**Entry point**: `index.html` — open directly in browser
**State**: MVP complete

## What it is
Bill of Materials tracker for hardware/electronics projects. Multiple BOMs, per-item product specs, image URL, pricing and shopping links for Amazon, Lazada, and AliExpress. Auto-calculates BOM total using cheapest available price per item. CSV export.

## Features
- Multiple BOMs (projects) with name + description
- Per item: name, quantity, specs/notes, image URL
- Platform links + prices: Amazon, Lazada, AliExpress
- Best price highlighted per item (★ marker)
- BOM total auto-calculated (cheapest per item × quantity)
- CSV export
- All data in localStorage, no server needed

## What could be added
- Drag to reorder items
- Duplicate BOM
- Import from CSV
- Currency conversion (Frankfurter API — free, no auth)
- Print/PDF view
