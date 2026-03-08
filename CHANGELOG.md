# Focus Frogs — Changelog

## v0.4.0 — Biomes & Expansion Update

### Biome System
- **5 unique biomes** each with distinct water colors, fog, particles, and specular highlights:
  - **The Pond** — classic deep blue, warm golden glow (starting biome)
  - **Frost Lake** — icy pale blue with cool white highlights
  - **The Swamp** — murky green with earthy tones
  - **Coral Reef** — deep ocean blue with pink/magenta coral highlights
  - **Lava Springs** — dark crimson with orange/amber lava glow
- Water rendering (stripes, highlights, specular) is now fully biome-aware
- Fog, ambient particles, and glow pools adapt to each biome's palette
- Minimap shows biome labels; locked biomes show "?" until bridges unlock

### Pad Expansion System
- **Start with 1 lily pad** per biome (was 5 hardcoded)
- **Expand up to 10 pads** per biome via the new EXPAND POND upgrade
- Pads unlock progressively — each expansion adds 1 pad to every biome
- **Bridge pads** (cross-biome connections) unlock at pad level 4
- Locked pads render as faint ghost outlines showing future positions
- Scaling costs: levels 1–3 cost 1 SP, levels 4–6 cost 2 SP, levels 7–10 cost 3 SP

### New Upgrades
- **Quick Hops** — reduces hop time (faster frog movement)
- **Deep Focus** — increases SP earned per focus session
- **Quick Rest** — shortens break timer duration
- **Expand Pond** — adds +1 pad per biome (up to 10)

### UX Improvements
- **Scrolling upgrade menu** — menu now scrolls to fit all items on 192px canvas
- **Upgrade descriptions** — selected item shows a desc line below the menu
- **Pad count HUD** — bottom-left shows "X/10 PADS" during gameplay
- **Locked pad hints** — faint outlines show where future pads will appear
- **Title screen info** — shows current pad count and achievement count
- **1-pad gameplay** — fruit can now spawn on frog's current pad when only 1 pad is active, with continuous collection checks

### New Achievement
- **LANDLORD** — expand your pond to the maximum (10 pads)

### Technical
- Added `BIOMES` constant with per-biome color palettes
- Added `isActive()` helper to check pad unlock status
- Added `biome()` helper to get current section's biome data
- `padLevel` added to save system (default 1, max 10) with migration
- `generateWorld()` refactored — pads tagged with `unlockLevel` (1–10)
- All game logic (hop targeting, fruit spawning, auto-hop) filters for active pads
- `drawWater()` uses biome colors instead of hardcoded palette
- `drawLilyPad()` accepts biome index parameter
- Minimap rendering updated for biome labels and lock states

---

## v0.3.0 — Sound, Poison & Achievements

- Added **sound effects** (hop, collect, level up, achievement, poison)
- Added **poisonous lily pads** that stun the frog
- Added **achievement system** with unlock notifications
- Audio context initializes on first user interaction

## v0.2.0 — Atmosphere & Lighting

- **Stardew Valley-style warm lighting** with golden glow pools
- Added **Geist Mono font** for text rendering
- Improved **text readability** with shadow outlines
- **Liminal atmosphere** with fog, moonlight, ambient particles
- **Map navigation** improvements and **mobile touch support**

## v0.1.0 — Initial Release

- Minimal frog pond pomodoro game
- 192×192 pixel art canvas
- Focus / Break / Long Break timer modes
- Auto-hop during focus sessions
- Fruit collection for XP and SP
- 5-section world map with minimap navigation
- Basic upgrade shop (Longer Focus, More Fruit, Frog Speed)
- localStorage save system
