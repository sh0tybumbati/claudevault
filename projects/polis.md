# Polis

**Local**: `~/projects/polis/`
**GitHub Pages**: https://sh0tybumbati.github.io/polis/
**Stack**: Phaser 3.87 (CDN), vanilla JS, no build step
**Entry point**: `index.html` — open via `live-server --port=3000`

## What it is
Greek city-state RTS inspired by Pyramida (Sokpop). Build your polis by day, hold the line at night. 50-second build phase → enemy wave from the north → survive 3 waves to win. Core differentiator is a formation system (phalanx, wedge, skirmisher screen) placed before and during battle.

## File layout

| File | Purpose |
|---|---|
| `js/scenes/GameScene.js` | Everything — world gen, units, buildings, AI, rendering (single large scene) |
| `GDD.md` | Game design document |
| `PLANNING.md` | Milestone roadmap |
| `CHANGELOG.md` | Feature history |
| `server/server.js` | Colyseus multiplayer skeleton (not wired to client yet) |

## Critical constants

```js
TILE = 32      // px per tile
MAP_W = 80     // tiles wide
MAP_H = 128    // tiles tall
MAP_OY = 52    // top offset px (topbar height)
```

## Key flags & gotchas

- `b.faction === 'enemy'` — marks enemy buildings (NOT `b.isEnemy`, which doesn't exist on buildings)
- `u.isEnemy` — flag on unit objects only
- Townhall `size: 2` → rendered at `s = TILE * 2 = 64px` — all drawing code must use 64px proportions
- **Drawing gotcha**: `cx` is absolute world x, never use it as a `fillRect` width — compute relative width as `cx - offset - px`
- `NODE_DEF.scrub.resource = null` — workers never target scrub nodes
- Workers seeking farms must guard `b.faction !== 'enemy'` in all three locations (`seekFarmerTask` ×2, `harvest_farm` replant fallback) — missing this caused workers to b-line to enemy farms

## Data structures

### Pastures
```js
b.males, b.females, b.lambs   // gender-aware counts (replaced old b.adults)
b.lambDays                     // day lambs were born; mature after 2 days
b.fedToday                     // set by shepherd; gates dawn breeding
b.woolTimer                    // days until next shear
```

### Wildlife
```js
d.ateToday     // portions eaten today (needs 3); reset at dawn
d.hungryDays   // consecutive hungry days; at 2 → isDead = true
d.grazeTarget  // id of target scrub node
```

### World maps
```js
visMap[y][x]      // 0=black, 1=dimmed, 2=lit (fog of war)
trafficMap[y][x]  // foot traffic count → desire paths at >120
roadMap[y][x]     // 1 = paved road
biomeData[y][x]   // 0=heartland, 1=scrubland, 2=forest, 3=badlands
```

## Shepherd priority order
1. Deposit carried wool
2. Feed unfed pasture (carry food → walk → set `fedToday=true`)
3. Transfer adult from full pen to underpopulated pen
4. Shear wild wool-ready sheep
5. Wander toward last sheep position
6. Tame wild sheep (prefers missing sex to balance breeding pair)
7. Slaughter surplus adults (culls extra males first)

## Implemented systems (as of 2026-04-19)

- Procedural world gen (biomes, river, resource node placement)
- Fog of war (`visMap`, three states, building vision radius, minimap mirrors fog)
- Minimap (bottom-right; terrain, fog, units as dots, buildings as squares)
- Tile speed modifiers + desire paths + paved roads
- Population: age stages (child→youth→adult), gender, house pairing requires M+F
- Full economy: farms, granary, woodshed, stone pile, worker haul loop, floor piles
- Formation system: LINE/WEDGE/SCREEN presets; box select; A/F/ESC shortcuts
- Pastures: gender-aware breeding, shepherd feeding (`fedToday`), pen transfer, wool, slaughter
- Living ecosystem: scrub nodes, berry bush regrowth/spread, tree saplings/seeding, wildlife foraging, hunger death (2 days), edge-entry spawning every ~90s
- Enemy mirror economy: workers gather/eat/respawn, `enemyRes` pool, AI build order (farm→barracks→archery→house), night raids

## Pending / next milestones

- Wildlife reproduction (male+female proximity → offspring)
- MS3 Economy Depth: Foodhaus, Mill, Bakery, Butcher, food chain buildings
- Counter-unit triangle (cavalry, spearman)
- Unit experience / veteran status
- Morale & routing
- Defensive structures (watch tower, wall gate)
- Multiplayer (Colyseus, MS5)
