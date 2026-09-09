# 3D Web Game Prototypes

This repository contains complete, self-contained single-file HTML5 3D Web Games built with **Three.js (r128)** and **Cannon.js (0.6.2)** physics:

1. **[Shipper4.html](file:///c:/Project/DnD/Shipper4.html)** — **Shipper 4: Procedural Environment & Map Generation System** (Dynamic Themes, Seed Sync, Procedural Layouts)
2. **[shipper3.html](file:///c:/Project/DnD/shipper3.html)** — **Shipper 3: Original Color Palette & Map-Wide Freeze Edition**
3. **[shipper2.html](file:///c:/Project/DnD/shipper2.html)** — **Shipper 2: Moving Out Edition**
4. **[Shipper.html](file:///c:/Project/DnD/Shipper.html)** — **Shipper 3D: 4-Player Delivery Driver Arena** (Original Dark/Industrial Theme)
5. **[index.html](file:///c:/Project/DnD/index.html)** — **Haul Masters 3D** (2-Player Red vs Blue)

---

# 🎲 Shipper 4 — Procedural Map & Dynamic Themes Edition (`Shipper4.html`)

A major evolution introducing a **Procedural Environment & Map Generation System** driven by deterministic multiplayer seed synchronization (**Mulberry32**):

### 🎯 Key Enhancements in `Shipper4.html`:
1. **Multiplayer Seed Synchronization**:
   - Single seed replicates exact layouts, wall configurations, obstacle placements, and visual themes for all players.
   - Displayed in top HUD badge (`[ICON] [THEME] #[SEED]`); clickable to re-roll seed anytime.
   - Supports URL query parameters (`?seed=12345&theme=warehouse`).
2. **4 Dynamic Visual Themes**:
   - 🏡 **Suburban Neighborhood**: Sunny skies, lush lawn, redwood picket fences, pine trees, and cutaway blue brick walls.
   - 🏭 **Industrial Warehouse**: Overcast gray skies, asphalt tarmac, chain-link security fences, oil drums, and corrugated metal walls with hazard yellow coping.
   - 🚧 **Construction Site**: Sunset amber haze, compacted earth/dirt terrain, orange safety mesh barriers, scaffolding towers, and raw cinderblock concrete walls.
   - 🏰 **Overgrown Estate**: Emerald twilight, mossy flagstone earth, ancient stone walls, tall gothic cypress trees, and ivy coping.
3. **Procedural Architectural Layouts**:
   - Scalable footprint (14.0m to 16.0m) with 4 open doorways.
   - 4 procedural interior partition archetypes (Quadrant Galleries, Lateral Wings, Staggered Corridors, Central Baffles).
4. **Balanced Extraction Zones**:
   - All 4 delivery hubs (Xanh SM, Grab, Shopee, Be) dynamically recalibrate their positions based on the building boundary: $\text{hubDist} = \text{buildingSize}/2 + 5.2\text{m}$, guaranteeing identical travel distances and perfect competitive balance.
5. **Round Lifecycle Triggers**:
   - Automatically builds fresh procedural layouts on match start, restart (`🔄`), or round advance.
6. **Pre-Game Map Theme Selection Popup**:
   - **Trigger Flow**: Automatically pops up immediately after a player selects their courier driver during pre-game setup (or clicks "NEXT: SELECT MAP THEME").
   - **5 Thumbnail Selection Tiles**:
     - 🏡 **Suburban Neighborhood**: Visual thumbnail preview with cozy homes, sunny daylight, and manicured green lawn stripes.
     - 🏭 **Industrial Warehouse**: Visual thumbnail preview with concrete shipping docks, steel girders, and blue atmospheric lighting.
     - 🚧 **Construction Site**: Visual thumbnail preview with sunset amber sky, dirt/gravel ground, hazard pylons, and scaffolding.
     - 🏰 **Overgrown Estate**: Visual thumbnail preview with misty twilight, ancient stone walls, moss, and courtyards.
     - ❓ **Random Theme (? Icon)**: Dynamic mystery card with animated gradient, sparkles, and a prominent bold `?` icon.
   - **Post-Round Map Rotation**:
     - Concluding a round presents "PLAY NEXT ROUND 🚀" and "CHANGE DRIVER / THEME 🔄".
     - When starting the next round, the map regenerates: preserving the chosen theme if Suburban/Warehouse/Construction/Estate was selected, or rolling a fresh surprise random theme if the "Random" option was picked!

---

# 📦 Shipper 3 — Original Color Palette & Map-Wide Freeze Edition (`shipper3.html`)

A complete, polished edition combining the cheerful suburban cutaway warehouse art style with the **original Moving Out color palette from the previous version**, and a strict **map-wide activity freeze** that pauses players, bots, physics, and match timers during the 3-2-1... FREEZE! countdown through to when the Slot Machine popup fades out.

### 🎯 Key Enhancements in `shipper3.html`:

#### 1. Original Suburban Color Scheme Restored
- Reverted all harsh/neon "pure vivid" overrides back to the original cheerful aesthetic.
- Balanced natural daytime lighting (`ACESFilmicToneMapping`, natural lawn greens, flat-shaded courier jackets).
- The four courier factions retain their distinct branding:
  - **Xanh SM**: `#3bbcb7` (West Hub • 🕊️ Wing Logo)
  - **Grab**: `#0cbb5e` (North Hub • 🛵 Grab Logo)
  - **Shopee**: `#fb5531` (East Hub • 🛍️ Bag Logo)
  - **Be**: `#ffcc00` (South Hub • 🐝 Be Logo)

#### 2. ❄️ Complete Map-Wide Freeze During Slot Machine Event
- **Instant Freeze on 3-2-1 Countdown**: When the event triggers (or when <kbd>M</kbd> / **🎰 SLOTS** is pressed), all player and bot movements freeze instantly (`velocity = 0`).
- **Suspended Activity**: Physics stepping, projectile arcs, puddle durations, and match timers pause.
- **Resume Only After Fade-Out**: Movement and physics remain completely frozen while the reels spin and resolve, resuming only after the slot machine popup fades out.

#### 3. 🎰 Slot Machine Item Event (Fixed & On-Demand)
- **Automatic Scheduled Drops**: The first Slot Machine event triggers **30 seconds into the match** (at `04:30`), then every 60 seconds thereafter!
- **Interactive "🎰 SLOTS" HUD Button**: Located directly in the top HUD next to the timer with a live countdown badge (`00:30`). Click it anytime to trigger the Slot Machine instantly!
- **Hotkey Support**: Press <kbd>M</kbd> at any point during gameplay to immediately test the 3-reel Slot Machine event!
- **3-2-1 Countdown & World Freeze**: Frosted blur overlay appears with retro countdown beeps. Physics, player movement, and match timer freeze solid.
- **3-Reel Arcade Slot Machine UI**:
  - 🔥 **Fire Extinguisher**: Hold Space to spray foam and freeze rivals for 10s!
  - ⚡ **Taser**: Electro-shock close rivals, paralyze for 10s & drop 50% cash!
  - 🥤 **Energy Drink**: Universal 2x speed boost for 20s across all carrying and pushing!
- **Sequential Reel Stops & Jackpot Fanfare**:
  - Reel 1 locks at 2.4s, Reel 2 at 3.7s, Reel 3 at 5.0s with mechanical clack ticks.
  - Multi-colored confetti burst, golden glowing borders, screen flash, and 6-note jackpot fanfare.
- **Arena Spawning**: The 3 rolled items spawn into the walkable arena floor with cash/item floaters, and world physics instantly resume.

---

# 📦 Shipper 2 — Moving Out Edition (`shipper2.html`)

A complete visual overhaul inspired directly by the hit party game **"Moving Out"**, combining cheerful suburban aesthetics, daylight sunny lighting, cutaway warehouse architecture, and rich environmental props with the competitive 4-player delivery mechanics of the four iconic courier factions (**Xanh SM**, **Grab**, **Shopee**, and **Be**).

### ðŸŽ¯ Latest Feature Updates:

#### 1. Updated Team Color Palette
- **Xanh SM**: `#3bbcb7` (West Hub &bull; ðŸ   Wing Logo)
- **Shopee**: `#fb5531` (East Hub &bull; ðŸ   Bag Logo)
- **Grab**: `#0cbb5e` (North Hub &bull; ðŸ   Grab Logo)
- **Be**: `#ffcc00` (South Hub &bull; ðŸ   Be Logo)

#### 2. ðŸŽ° Slot Machine Item Event (Replaces Mystery Boxes)
- **Countdown & World Freeze**: Every 1 minute during the 5-minute match, a **3-2-1 countdown** appears with audio beeps. At zero, match timer, character movements, and world physics freeze completely!
- **3-Reel Arcade Slot Machine UI**: An arcade slot machine cabinet pops up displaying 3 spinning reels with the combat gadgets:
  - ðŸ”¥ **Fire Extinguisher**: Spray foam to freeze rivals for 10s!
  - âš¡ **Taser**: Electro-shock close rivals, paralyze for 10s & drop 50% cash!
  - ðŸ¥¤ **Energy Drink**: Universal 2x speed boost for 20s across all carrying and pushing!
- **Sequential Reel Stop (Anticipation & Hype)**:
  - Reel 1 locks at `t = 2.4s` with a crisp mechanical CLACK audio tick and bounce animation.
  - Reel 2 locks at `t = 3.7s` with CLACK tick and bounce.
  - Reel 3 locks at `t = 5.0s` with CLACK tick and bounce.
- **Dramatic Reveal Burst (Jackpot Fanfare)**:
  - Screen flash effect triggers across the screen.
  - Multi-colored confetti burst explodes over the cabinet.
  - Golden glowing pulsing highlight borders envelop all 3 winning reel frames.
  - Energetic 6-note jackpot fanfare plays.
- **Arena Spawning & Seamless Transition**:
  - The 3 resolved items spawn at random walkable locations across the house and pathways.
  - World unfreezes seamlessly and match resumes! Total event duration is tightly tuned to **8â€“10 seconds**.

#### 3. ðŸƒ Movement Speed Re-tuning (75% of Previous Velocity)
Movement speeds have been re-tuned down by 25% (to **75% of previous speed**) for deliberate, tactical character movement:

| Speed Tier | Velocity | Multiplier & Condition |
| :--- | :--- | :--- |
| **Normal Speed** | **5.4 m/s** | Default unencumbered walk, or carrying Light/Fragile parcel |
| **Sprint Speed** | **8.1 m/s** | Holding <kbd>SHIFT</kbd> (1.5x boost, drains stamina) |
| **Slow Speed** | **2.7 m/s** | Pushing Heavy cargo (50% base speed) |
| **Bot Walk Speed** | **5.1 m/s** | Base bot patrol velocity |

*Walk cycle cadence is synchronized (`cycleSpeed: 10.1` sprint / `6.2` walk) to eliminate foot-sliding.*

#### 4. â¸ï¸ In-Game Pause & ðŸ”„ Restart Controls
- **Pause Button `â¸`**: Located in the top-right HUD. Also press <kbd>P</kbd> or <kbd>Esc</kbd> to freeze gameplay, suspending timer, physics, and bot movements, and showing the frosted Pause Modal.
- **Restart Button `ðŸ”„`**: Located in the top-right HUD and in the pause modal to immediately reset and restart the 5-minute shift without page reloading.

---

### ðŸŽ® Controls Guide

| Action | Keyboard Input |
| :--- | :--- |
| **Move Driver** | <kbd>W</kbd><kbd>A</kbd><kbd>S</kbd><kbd>D</kbd> or Arrow Keys |
| **Sprint / Speed Boost** | Hold <kbd>SHIFT</kbd> (1.5x speed boost; stamina restores in 2s upon release) |
| **Pause / Resume Match** | Press <kbd>P</kbd> or <kbd>Esc</kbd>, or click the Pause `â¸` icon in top HUD |
| **Restart Match** | Click the Restart `ðŸ”„` icon in top HUD or pause menu |
| **Interact / Grab Gadget / Grab Cash** | Press <kbd>F</kbd> |
| **Pick Up Light / Fragile Order** | Left-Click on parcel, or press <kbd>SPACEBAR</kbd> |
| **Drop Carried Order** | Press <kbd>SPACEBAR</kbd> (âš ï¸ Drops fragile item to shatter!) |
| **Push / Drag Heavy Cargo** | Hold/Press <kbd>SPACEBAR</kbd> near heavy cargo |
| **Consume / Use Equipped Gadget** | Press / Hold <kbd>SPACEBAR</kbd> (Drink Energy Can, Zap Taser, Spray Foam) |
| **Toggle Audio** | Click top-right Speaker Icon |