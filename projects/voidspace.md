# Voidspace

**GitHub**: https://github.com/sh0tybumbati/voidspace
**Local**: not cloned locally (online only — clone before working on it)
**Stack**: Next.js 14 (App Router), Node.js + Express, PostgreSQL, Redis, Prisma ORM, NextAuth.js + JWT, S3-compatible storage, Turborepo monorepo
**State**: ~60–70% — Phase 1 + Phase 2 complete, Phase 3 (frontend) partially built.

## What it is
Community discussion platform — Reddit alternative with democratic governance, transparent moderation log, public mod action appeals, and community-controlled ads with revenue sharing. Platform only removes illegal content; communities self-moderate.

## What's built (confirmed from repo)

### Phase 1 — Auth ✅
- User registration/login, JWT, NextAuth.js

### Phase 2 — Backend ✅
- Spaces (communities): CRUD, subscribe/unsubscribe, rules, NSFW marking
- Posts: text/link/image/video, voting (smart toggle logic), hot score algorithm
- Comments: threaded (depth tracking), voting
- Hot score background job (every 15min, Reddit-style decay formula)
- Alignment score background job (every 5min)
- Moderation: mod actions, ban detection, permission system (founder/mod roles)
- 24 REST API endpoints, fully tested

### Phase 3 — Frontend (partial) 🔄
Files exist for: PostCard, PostForm, VoteButtons, CommentTree, Comment, CommentForm, UserProfile, AlignmentDisplay, spaces pages, search, settings, admin, saved, submit. Some may be stubs — needs audit.

## What's missing
- Clone locally and audit what actually renders
- Redis caching (may not be wired)
- S3 file storage (image/video uploads)
- Democratic mod election system (in README, unclear if built)
- Production deploy

## Commercial potential
MEDIUM — differentiated concept (democratic moderation) but needs network effects. Long-term play. Not near-term revenue — needs other projects generating income first.
