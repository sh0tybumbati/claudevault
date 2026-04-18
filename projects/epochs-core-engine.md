# Epochs Core Engine

**Status**: Design / pre-production (no code yet as of 2026-04-19)
**Engine**: Redot 4.3 (Godot fork)
**Docs in**: `/sdcard/Download/` — `# The Hot Gates - Game Design Document FULL.pdf`, `game_series_lore.docx`

## What it is

A four-game series sharing a common engine, dual-arm radial control system, and Ki metaphysics. Each game is standalone but systems deepen progressively across the series. Generational roguelike progression is the through-line — you always continue as a descendant when a character dies.

## The Four Games

| # | Title | Setting | Aesthetic |
|---|---|---|---|
| 1 | **The Hot Gates** | Ancient Sparta, 490–480 BC | 3D cel-shaded Greek pottery (terracotta/black) |
| 2 | **Jade Mountain** | Ancient China, Xiaolin cultivation | Eastern ink scroll paintings |
| 3 | **Age of Titans** | Primordial prehistory, megafauna | Moebius-inspired cosmic landscapes |
| 4 | **New Albion** | Technomagical space exploration | Friendly WH40K, cyan/purple heraldic |

---

## Shared Systems

### Dual-Arm Radial Control
The core innovation across all games. Each arm controlled independently:
- **Angle**: 0–360° around character's vertical axis
- **Extension**: retracted → full reach (mouse wheel)
- **Both clicks held**: control both arms simultaneously
- Mouse/stick circular movement creates natural swinging arcs
- IK: two-bone skeletal system; shoulder is radial pivot; hand = angle + extension
- **Grip system**: grip strength depletes with heavy weapons; builds through training

### Ki Metaphysics (shared across all four games)
Ki exists on a spectrum: pure life energy (positive) ↔ pure death energy (negative).
- **Mortals**: predominantly positive Ki + small death reserve
- **Undead**: predominantly negative Ki
- **Benevolents**: pure positive Ki; stone statues, spirit manifestations, transcended elder animals; cannot be created through violence — only through long life and spiritual development
- **Malevolents**: pure negative Ki; volatile, contagious; spread Ki corruption cascades to surrounding biomes, triggering undead outbreaks
- Biome health = average Ki of all wildlife in the area; affects colour, atmosphere, spirit manifestations

### Generational Legacy
- Character death is permanent; play continues as descendant/successor
- **Carries forward**: knowledge/techniques (as skill fragments / muscle memory), estate infrastructure, spiritual cultivation, reputation, equipment as heirlooms
- The series as a whole = arc of one lineage from Thermopylae to the stars

### Entity Composition System
Layered anatomy: Equipment → Armor → Clothing → Skin → Muscle → Bone → Organs
- Each layer has material properties; damage propagates through layers
- **Damage permanence by game**:
  - Hot Gates / Jade Mountain: permanent injury, no replacement
  - Age of Titans: tribal succession absorbs the loss
  - New Albion: sparkcraft prosthetics with runic interfaces (functional replacement + new capabilities)

---

## Game 1: The Hot Gates (most developed)

### Premise
Generational roguelike through one Spartan lineage, culminating at the Battle of Thermopylae (480 BC). Everything before the pass is the prologue. Post-Thermopylae = endless legacy mode.

### Camera zoom levels (4)
1. **Third-person ARPG** — over-shoulder, full dual-arm combat
2. **Tactical squad view** — pull back ~10–15m, formation commands
3. **Strategic army view** — top-down/isometric, Rome: Total War–style RTS
4. **Grand strategy** — territory map, estate/city builder, diplomacy

### Spartan life stages
1. **Agoge (ages 7–20)** — tutorial; teaches all mechanics through Spartan military training
2. **Crypteia (ages 20–21)** — stealth phase; morally complex helot-hunting missions; player choices affect personality and helot relations for rest of the game
3. **Full citizenship (age 21+)** — main gameplay; estate management, syssitia obligations, military campaigns, assembly politics, marriage/family

### Key societies
- **Spartiates** (full citizens) — bound by syssitia (monthly food contribution to mess hall); fail = lose citizenship
- **Helots** — enslaved underclass, ~7:1 ratio; they remember your Crypteia actions across generations; morale → rebellion risk
- **Perioikoi** — free non-citizens, craftsmen/traders/soldiers
- **Persians** — off-screen antagonist until Thermopylae climax

### Thermopylae event
- Fixed at 480 BC; happens once per save file
- Selection criteria: having sons to continue the line, age, military record, syssitia standing
- Three days of compressed fighting → inevitable death
- Legacy score from the battle affects descendants

### Stances
Combat: Hoplite, Skirmisher, Dual Wield, Pankration, Archer
Work: Woodcutting, Mining, Crafting, Farming

### Phalanx mechanics
- Othismos: pushing contest between formations; density = power
- Shield overlap protects neighbours; gaps are fatal
- Second rank strikes over first rank
- Individual can break formation for heroic action (risk/reward)

### Inheritance
- **Genetic** (immutable): body proportions, physical potential, appearance
- **Epigenetic** (parent's life bleeds in): muscle development, grip strength, stress responses
- **Skill fragments**: muscle memory affinity for parent's weapons/techniques
- **Material**: kleros (land + helots), equipment as heirlooms, buildings, wealth
- **Social**: syssitia standing, political connections, blood feuds, helot relations

### Price / model
$49.99, no microtransactions; premium single-purchase

---

## Game 2: Jade Mountain

### Chakra System (7 chakras → 7 personality spectrums → elemental affinities)
| Chakra | Element | Shape | Positive | Negative |
|---|---|---|---|---|
| Root | Earth | Red square | Stability, patience | Stubbornness, paralysis |
| Sacral | Water | Orange pentagon | Passion, creativity | Obsession, manipulation |
| Solar Plexus | Fire/Plasma | Yellow hexagon | Confidence, leadership | Tyranny, cruelty |
| Heart | Air | Green hexagon | Empathy, compassion | Bitterness, spite |
| Throat | Space | Blue heptagon | Honesty, teaching | Deception, manipulation |
| Third Eye | Mind | Indigo octagon | Insight, vision | Paranoia, madness |
| Crown | — | — | (not yet documented) | — |

- Characters have a **dominant chakra** shaping behaviour and combat style
- Each arm can channel a different element independently → dual-element techniques for advanced practitioners
- **Space element** = teleportation to known locations
- **Mind element** = astral projection, aura reading, limited temporal effects (single-player only)
- Can only fully master **one element** — spreading too thin limits peak capability
- Elder animals accumulate chakra and can become benevolents (stone statues embedded in landscape)
- Can import Hot Gates bloodline for reincarnation benefits

---

## Game 3: Age of Titans

- Primordial world; human tribes vs megafauna spiritual entities
- Elder megafauna accumulate chakra over centuries (a mammoth matriarch may outpower any human shaman)
- Ancient predators → malevolents; ancient herbivores → benevolents
- Soul reincarnation affects physical development; spiritual history of a lineage bleeds into descendants' bodies
- Tribal breeding of animals can develop traits reflecting spiritual work of handlers
- Lore gap: tribes, megafauna species, antagonist, narrative arc not yet documented

---

## Game 4: New Albion

### Anglish tech lexicon (Germanic-root English, no Latinate words)
| Anglish | Meaning |
|---|---|
| Reckoner | Computer |
| Reckon gem | Processor/CPU |
| Runeblock | Data storage |
| Runewright | Software developer |
| Thinkwright | Hardware engineer |
| Sparkcraft | Electricity |
| Sparkways | Electrical conduits/wires |
| Wardplate | Powered armour |
| Glowbrand | Energy sword |
| Ironstone | Metal ore (grey/red/white/yellow variants) |
| Lodestone | Natural magnet |
| Lodefield | Magnetic field |

- Procedurally generated alien biology (silicon bones, crystalline scales, energy organs, distributed nervous systems)
- Genetic engineering available; bio-mechanical hybrids
- Sparkcraft prosthetics with runic interfaces replace lost limbs (may add capabilities)
- Lore gap: civilisation history, named houses/factions, antagonist forces, alien worlds — very thin documentation

---

## Lore gaps (as of 2026-04-19)
- Hot Gates: agoge curriculum, named NPCs, Spartan political factions (kings, ephors, gerousia), helot storylines
- Jade Mountain: named factions, monasteries, political structures, antagonist, narrative arc
- Age of Titans: nearly everything narrative
- New Albion: nearly everything narrative
