# Space Game

**Local**: `~/projects/space-game/`
**GitHub**: (repo exists, minimal commits)
**State**: 30% — early prototype
**Stack**: Phaser 3.87, Vite 5, vanilla JS
**Dev server**: `cd ~/projects/space-game && npm run dev`

## What it is
Space physics simulation / game. Orbital mechanics sandbox with realistic N-body physics, Lagrange point calculations, and manual spacecraft control.

## Scenes
- `BootScene` — asset loading
- `GameScene` — main gameplay

## Entities
- `Ship` — player spacecraft with thruster physics
- `CelestialBody` — planets, moons, stars

## Notable systems
- Manual physics (no Phaser built-in gravity)
- Lagrange point solver (`lagrange.js`) — L1–L5 calculations
- Orbital mechanics (`orbital.js`) — realistic velocity/acceleration
- Dual joystick UI — two simultaneous touch inputs for mobile
- HUD system — real-time flight instrumentation

## State
Too early to productize. Focus on other projects first.
Come back when Silicon Tycoon and YieldDesk are generating revenue.
