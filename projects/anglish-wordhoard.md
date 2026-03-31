# Anglish Word-hoard

**Local**: `~/projects/Anglish-Word-hoard/`
**GitHub**: https://github.com/sh0tybumbati/Anglish-Word-hoard
**Stack**: React 18 + TypeScript + Tailwind + Vite + Fuse.js

## What it is
Interactive digital dictionary for Anglish — English rewritten using only Germanic vocabulary (replacing Latin/French loanwords). Aligned with the Anglish community standard at wordbook.anglish.org.

## Features
- Fuzzy search (Fuse.js) across words, meanings, etymology, grammar
- Rich etymology with Old English / Proto-Germanic roots and cognate cross-references
- Attestation levels: Attested, Reconstructed, Neologism, Proposed
- Grammatical classification: N, V, AJ, AV, PREP, CONJ, PRO, PART, PREF, SUFF, PHR
- Card view + scholarly table view
- Favorites (localStorage)
- JSON export of full database
- Neo-archaic design: Gothic typography (UnifrakturMaguntia), holographic effects
- Mobile responsive

## Planned: Morpheme Catalogue (not started)
Two datasets to add:
1. **Latin/Greek morpheme catalogue**: `bio-`, `cardio-`, `-ology`, `-itis`, etc. → meaning → Anglish equivalent
2. **Anglish prefix/suffix catalogue**: `un-`, `-ness`, `-hood`, `-dom`, etc.

Implementation:
- New file: `src/data/morphemes.ts` with `MorphemeEntry` type
- Anglisher decomposition: strip known affixes, show breakdown tooltip
- Separate tab for browsing morphemes

**Why**: Medical/scientific terms are almost entirely Latin/Greek compounds. Morpheme decomposition lets users Anglish-ify them component by component.

## Productization options
- Gumroad one-time purchase ($5–10) for offline version
- Paid API for developers building language tools
- Patreon for ongoing word additions
- Electron wrapper for desktop app
