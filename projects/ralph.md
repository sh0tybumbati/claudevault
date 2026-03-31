# Ralph — Autonomous Claude Code Loop

**Local**: `~/ralph-claude-code/`
**GitHub**: https://github.com/sh0tybumbati/ralph-claude-code
**Version**: v0.11.5
**Stack**: Pure Bash 4.0+, Claude Code CLI, tmux, jq, git
**Listed in**: Awesome Claude Code community list

## What it is
Autonomous development loop for Claude Code. Runs Claude Code continuously with intelligent exit detection, rate limiting, and circuit breaker pattern. Enables unattended AI-driven development sessions.

## Install
```bash
cd ~/ralph-claude-code && npm install -g .
# or: ~/.local/bin/ralph is already in PATH via ~/.bashrc
```

## Run (in a project)
```bash
cd ~/projects/silicon-tycoon
ralph --live   # live streaming output
ralph          # quiet mode
```

## Key features
- **Dual-condition exit**: requires BOTH completion indicators AND explicit EXIT_SIGNAL
- **Rate limiting**: 100 calls/hour (configurable), hourly reset
- **Circuit breaker**: CLOSED → HALF_OPEN → OPEN states, auto-recovery
- **Session continuity**: context preserved across iterations, 24-hour expiry
- **5-hour API limit handling**: detects and waits automatically in unattended mode
- **tmux integration**: real-time monitoring dashboard
- **Task import**: from GitHub Issues, beads task system, PRD documents
- **File protection**: RALPH_REQUIRED_PATHS validation

## Silicon Tycoon config
```
~/projects/silicon-tycoon/.ralph/PROMPT.md    — task instructions
~/projects/silicon-tycoon/.ralph/AGENT.md     — agent behavior rules
~/projects/silicon-tycoon/.ralph/fix_plan.md  — current fix plan
~/projects/silicon-tycoon/.ralphrc            — configuration
```

## Productization potential
- Enterprise dev shops would pay for managed Ralph runs (SaaS)
- GitHub Marketplace action
- Premium features: analytics, team collaboration, Git integration
- 566 tests, 243 commits — production-ready foundation
