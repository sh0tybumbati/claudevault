# Okibar

**GitHub**: https://github.com/sh0tybumbati/Okibar
**State**: 30% complete (early prototype, 5 commits)
**Stack**: Node.js, Socket.io, YouTube API

## What it is
Karaoke bar management system. YouTube song integration (free content), real-time queue sync via Socket.io, separate singer management view and public display view.

## Architecture
- Singer management view (bartender/host)
- Public display view (TV/projector showing current queue)
- Real-time sync via Socket.io
- YouTube as song source (no licensing cost)

## Market
- Every karaoke bar globally
- KTV establishments (massive market in Asia)
- Event venues with karaoke nights
- **Pricing**: $100–500/month per location as SaaS

## Why it's interesting
YouTube integration means zero music licensing cost — existing POS karaoke systems are expensive ($5k–$20k hardware) and have limited song libraries. A browser-based system with YouTube as the backend disrupts this completely.

## What needs building
- Song search and queue management UI
- Singer rotation logic
- Payment/subscription integration
- Performance management (current singer timer, next up display)
- Basic admin (song blacklist, venue settings)
