# Working with sh0tybumbati

## Communication style
- Direct and concise — no filler, no preamble, no trailing summaries
- Don't restate what they said — just do it
- They can read the diff — don't explain what you just changed line by line
- Use markdown tables and bullet points over prose walls
- Short sentences preferred

## Autonomy
- They give broad latitude ("do whatever you want", "your choice") — be opinionated and execute
- Don't ask for permission on every step — make reasonable decisions, act, report outcome
- They course-correct if something's wrong — this is expected and fine
- Don't propose before acting on obvious/safe things

## When to ask
- Before spending money or touching production infra for the first time
- When a decision has large irreversible consequences
- When two reasonable paths diverge and both have real tradeoffs
- For UI tasks they must do manually (Itch.io, Stripe dashboard) — babystep them through clearly

## Babystep format (for UI tasks)
When the user needs to click through a UI:
- Numbered steps
- Exact field names and values
- Note anything non-obvious
- Tell them what to look for to know it worked
- Stay available for questions during

## Code style
- No unnecessary comments or docstrings
- No defensive error handling for impossible scenarios
- No premature abstraction
- No backwards-compatibility shims
- Don't add features beyond what was asked
- Prefer editing existing files over creating new ones

## Standing behaviors
1. **After meaningful code changes**: update CHANGELOG, README, FEATURES.md, PLANNING.md (use `update-docs` skill)
2. **Silicon Tycoon live-server**: always port 3000, never 8080 (8080 breaks architecture page)
3. **YieldDesk Pro features**: keep hidden until Stripe is wired — no upgrade prompts visible to users

## Skills to use
- `update-docs` — after any non-trivial code change
- `update-config` — for settings.json changes

## What they're good at / will handle themselves
- Game design and mechanics decisions
- 3D design and printing
- Itch.io publishing, Stripe dashboard setup
- Business decisions

## What Claude should handle
- All code writing and debugging
- Deployment (Render API)
- GitHub repo management
- Product copy and descriptions
- SEO and marketing text
- Research
