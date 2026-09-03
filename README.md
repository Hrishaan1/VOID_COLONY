# VOID COLONY — Space Explorer

An arcade-style space colonization and economy simulation game built entirely for the browser. Pilot your ship through a dynamically simulated solar system, establish thriving resource colonies on planets and moons, trade in speculative financial markets, and defend your infrastructure from hostile enemy fleets.

Live Demo: [void-colony.org](https://void-colony.org)

## 🌌 Core Features

- **Real-time Orbital Physics:** A living solar system featuring a central star with planets and moons locked into real-time circular orbital rings. Proximity mechanics tie your ship seamlessly into a planet's drift vector.
- **Dynamic Module Economy:** Land on celestial bodies to build modular infrastructure. Utilize structural slots dependent on planetary size to scale up your operations:
  - **Farms:** Generate raw Food cargo passively (requires player proximity to harvest).
  - **Fuel Generators:** Recharge ship fuel stores at the cost of your food supply.
  - **Laboratories:** Unlock a multi-tier permanent research tree to upgrade your ship, automation, and tech.
- **Advanced Space Station & Weapon Systems:** Dock at the neutral space station to purchase, equip, and customize advanced weaponry including the Pulse Wave, Railgun, Gravity Well Launcher, Kinetic Flak Cannon, Solar Beam Overdrive, Overcharged Shield Burst, and exotic passive abilities like **Infinity** and **Time Stop**.
- **Logistics & Trade Networks:** Purchase AI-controlled freighters to automate food hauling from your colonies back to the central hub for steady credit income. Defend them from raider ambushes in dedicated escort missions.
- **Epic Boss Encounters & Diplomacy:** Face off against world-threatening bosses like the resource-siphoning **Leviathan Mothership**—which can be bargained with via an RPG-style dialogue system—and the massive **Fleet Admiral Command Ship**.
- **Cross-Platform Control Interfaces:** Play with highly accurate standard mouse-aim tracking, classic keyboard arcade mechanics, or use the specialized virtual joysticks and touch configurations optimized for mobile screens.

---

## 🎮 How to Play & Controls

### Keyboard & Mouse Controls
| Input | Action |
| :--- | :--- |
| **W** / **↑** | Thrust Forward |
| **A** / **D** or **←** / **→** | Rotate Ship Direction |
| **S** / **↓** | Engage Retro-Brakes (Slow Down) |
| **E** | Interact / Dock with nearby Planet, Moon, or Space Station |
| **SPACE** / **Left Click** | Fire Currently Equipped Active Weapon |
| **C** | Toggle Mouse Aim Mode (Ship tracks cursor position) |
| **M** | Toggle Interactive Solar System Map overlay |
| **P** | Pause / Open Market and Portfolio Interface |

### Mobile Touch Controls
- **Left Virtual Joystick:** Continuous steering and thrust management.
- **DOCK Button:** Contextual interaction with celestial bodies in immediate proximity.
- **BRAKE Button:** Instantly drops current velocity.
- **MAP Button:** Toggles the full-screen interactive planetary navigation display.

---

## 🛠️ Architecture & System Design

The game engine is built around a lightweight, native JavaScript web configuration utilizing the HTML5 Canvas API for smooth 60 FPS vector rendering, paired with explicit UI overlays driven by CSS Flexbox layouts.

### 1. State Persistence
An automated auto-save sequence syncs the state of the player's core attributes (`Hull Integrity`, `Fuel`, `Food Supply`, `Credits`), established colony tracking, research progression, and building counts to browser-level `localStorage` every 5 seconds.

### 2. Proximity & Docking Matrices
Planets enforce a "Sphere of Influence". When a ship breaks into this boundary, a tracking matrix dampens absolute spatial coordinates and anchors the ship relative to the parent planet's current orbital velocity drift vector. Collision envelopes trigger physical bounce responses on direct surface contact, which can be weaponized into high-velocity **Divergent Rams**.

### 3. Asynchronous Market Tasks
Interval threads decouple the game loops from economic shifts. The Food Market updates prices every 60s using localized trends, while the Solar Bond ledger tracks moving averages and portfolios over a separate 30s polling thread.

---

## 📝 Changelog & Patch Notes

### v1.18 — Deadly Sentencing (Domain Expansion)
- Added **Deadly Sentencing**, Higuruma's Domain Expansion, as the ultimate primary weapon (Space Station, 15,000¢).
- Activating the domain plunges the surrounding battlefield into **pitch black**, a sealed golden arena.
- Inside the domain, **all attacks are forbidden** — your weapons and every trapped raider's weapons fall silent.
- Trapped raiders are **bound inside the domain** and cannot exit, and no new hostiles can meaningfully enter.
- An **interactive sentencing dialogue** opens automatically, charging the accused with crimes against international space treaties.
- Each defendant responds with a random plea — they either **confess**, **stay silent**, or **deny**.
- Listen to their testimony and **pick the response that matches** their plea:
  - **Confess** → sentence them **GUILTY**.
  - **Silent** → treat their silence as admission, sentence **GUILTY**.
  - **Deny** → without proof, acquit them **NOT GUILTY**.
- Deliver the matching verdict to earn the **Executioner's Sword**; a wrong ruling collapses the domain with no reward.
- The moment you receive the sword, the **domain collapses** back to the normal battlefield.
- With the sword active, the ship **pulsates gold** and your primary attack becomes a **dash forward that instantly obliterates** every raider in its path (no Black Flash).
- The sword lasts **30 seconds**; the domain enters a **1-minute cooldown** that begins once the sword expires.

### v1.17 — Fleet Admiral Ship
- Added the Fleet Admiral Ship as a new high-threat boss encounter with a distinct warning and warp-in effect.
- The Fleet Admiral is larger than the Leviathan, uses dark gold command-ship trim, and hunts the player's most populated colony.
- **Carrier Inbound:** Opens hangar bays every 20 seconds and launches 2-3 enemy raiders.
- **Laser Strike:** Locks onto the player, shows a red targeting warning, then fires a continuous high-damage beam.
- **Infinity Synergy:** Infinity blocks the admiral laser, causing the beam to stop, distort, and split at the barrier perimeter.

### v1.16 — Time Stop
- Added Time Stop as a late-game passive station weapon.
- Press fire with Time Stop equipped to freeze planets, freighters, escorts, raiders, and hostile fire in place.
- Time Stop consumes food rapidly while active and collapses when reserves run out.
- Black Flash rewards gained during stopped time are held and released when time resumes.

### v1.15 — Expanded Research Tree
- Added tier-2 and tier-3 Laboratory technologies for logistics, construction, jump travel, shields, and exotic weapons.
- New research can expand fuel and food capacity, reduce build and jump costs, improve freighters, and strengthen advanced weapons.
- Older saves automatically receive default levels for the new technologies.

### v1.14 — Infinity
- Added Infinity as a passive space station weapon.
- Press fire with Infinity equipped to toggle a repulsion field around the ship.
- Enemy projectiles and raiders are pushed away when they press into the field.
- Infinity radius can be customized with a station slider and scales with higher food activation costs.
- Active Infinity drains 0.5 food per second.

### v1.13 — Advanced Weapon Systems
- Added Gravity Well Launcher, Kinetic Flak Cannon, Solar Beam Overdrive, and Overcharged Shield Burst.
- **Gravity Well Launcher:** Pulls nearby raiders into a temporary trap for easier Divergent Ram setups.
- **Kinetic Flak Cannon:** Fires short-range shrapnel with heavy knockback; unlocks after 3 active farms.
- **Solar Beam Overdrive:** Channels scaling damage while consuming food and locking ship movement completely stationary.
- **Overcharged Shield Burst:** Clears enemy projectiles and disables nearby raider engines as a defensive panic button.

### v1.12 — Leviathan Diplomacy
- Massive hostile Motherships can warp in and siphon nearby colony resources.
- Added negotiation choices using Credits, Food, raider kills, or Laboratory Modules.
- Failed diplomacy starts component combat against the Leviathan engines and hangar.
- **Quantum Rewind:** Can revive a destroyed hull by sacrificing Credits or a built module.

### v1.11 — Divergent Ram
- Added high-speed Collision Drive impacts against enemy raiders.
- Divergent Ram gives fuel back, triggers hit stop, and vaporizes most raiders on impact.
- **Black Flash:** High-speed impacts distort targets with dark lightning effects and leave residual ship afterimages.
- Low-speed enemy collisions now punish the hull instead of becoming free damage.

### v1.10 — Trade Routes & Freighters
- Added purchasable AI freighters unlocked after you establish multiple colonies.
- Freighters automatically haul food from farm colonies to the central hub for credit gains.
- Added escort missions when raiders attempt to ambush loaded freighters.
- Freighters are bulkier, slower variants of the player ship and appear directly on the map display.

### v1.9 — Void Events
- Added random Solar Flares that temporarily disrupt the overlay map or mouse aim functions.
- Added mineable passing comets with large credit rewards if you match their orbital velocity.
- Added rare paired wormholes that shortcut across distant solar orbits.

### v1.8 — Space Station Weapons
- Added a neutral space station near the system center.
- Dock at the station to buy and equip Pulse Wave or Railgun weapons.
- Pulse Wave deals short-range area-of-effect damage; Railgun hits hard at long range and consumes ship fuel.

### v1.7 — Laboratory Research
- Added Laboratory modules and a permanent research progression tree.
- Research can improve engine output, farm automation, shields, weapons, and maximum hull integrity.
- Shielding adds a passive recharging blue shield bar layered above hull integrity.

### v1.6 — Galaxy Starmap
- Added a draggable galaxy starmap with selectable nearby solar systems.
- Jump costs scale dynamically with each system's distance from the home system coordinates.
- Visited systems and systems with active colonies are permanently marked on the starmap.
- New nearby systems appear dynamically as you push deeper into the galaxy.

### v1.5.2.1 — Laser Firing Bug Fix
- Lasers weren't firing due to a weapon cooldown bug—this has been fixed.

### v1.5.2 — Combat Rebalance
- Enemy ships now roam peacefully—they won't attack unprovoked.
- Enemy ships retaliate only if you shoot them first.
- Reclaiming an enemy planet triggers a retaliator ship to spawn.
- Ambient roamers drift naturally between planets instead of idling in place.
- Hull integrity now regenerates slowly over time (2 HP/sec).

### v1.5.1 — Mouse Aim Mode
- Press `C` to toggle mouse aim — ship rotates to face your cursor.
- Click to fire in mouse aim mode (crosshair cursor shown).
- Dotted targeting line drawn from ship to cursor.
- Thrust and brake controls remain unchanged in mouse mode.

### v1.5 — Enemy Raiders & Combat
- Enemy raider ships spawn every 45s (up to 5 at a time).
- Enemies fly to planets, capture them, and destroy your modules.
- `SPACE` / 🔴 button fires cyan laser bolts at enemies.
- Destroying an enemy earns a 40¢ bounty.
- Added Hull Integrity health tracking — takes damage from enemy fire.
- Enemy-owned planets are marked with a red orbit ring display.
- Reclaim captured planets for 80¢ from the planetary panel interface.
- Enemy ships display a live HP bar and claim-progress bar in the world view.

### v1.4.1 — Solar Bonds
- Added Solar Bond market — buy & sell speculative bonds for profit.
- Bond prices fluctuate every 30 seconds with random surges & crashes.
- Portfolio view shows unrealised P&L, average buy price & live price chart.
- Bond market fully accessible directly from the Pause menu.

### v1.4 — Economy & Menus
- Added Credits currency tracking — colonising costs 20¢, farms 50¢, fuel gens 80¢.
- Food Market introduced with fluctuating baseline prices updating every 60s.
- Food sell-ratio slider integrated into HUD — split harvest between stock and credits.
- Fixed: sell ratio now correctly scales with the absolute number of farms.
- Pause menu implemented (`P` key or ⏸ button) — access markets, view stats, or quit to title.
- Patch Notes screen made accessible from both the pause overlay and the title menu.

### v1.3.2 — Farm Harvesting
- Farms only produce food when the ship is within the specified harvest range.
- Green dashed harvest-range ring rendered around farm planets.
- Farm slot label shows live harvesting/idle status updates in the planet panel.

### v1.3.1 — Moon Balance
- Moon sphere of influence reduced to 40% of standard planet proximity.
- Moon interact range halved — no longer hijacks planet approach sequences.
- Moon orbits start further from planet surface (60px minimum radius boundary).
- Wider spatial spacing enforced between multiple moons around the same planet.

### v1.3 — Proximity & Resource Update
- Orbital co-movement: entering proximity locks ship to planet drift exactly.
- Planet collision physics implementation — ship bounces off structural surfaces.
- Fuel generators cost 1 food/sec while actively refueling the ship hull.
- Passive food consumption added representing crew upkeep (0.08 units/sec).
- Food supply warning notification triggers when reserves hit absolute zero.

### v1.2.1 — Map Fixes
- Fixed map canvas only showing top strip — now fills the panel correctly.
- Map reads wrapper dimensions dynamically after CSS flex layouts are fully applied.
- Map auto-fits to system scale on open via native `requestAnimationFrame`.
- Mobile: map opens fullscreen; touch pan & pinch-zoom fully supported.

### v1.2 — Solar System & Map
- Full solar system layout — named star at center with distinct orbital rings.
- Planets orbit in real time; moons follow designated planetary orbits.
- Moons are colonizable with 1 infrastructure slot each; planet panel outlines its moons.
- Floating draggable map (`M`) added with scroll-to-zoom and click-to-warp mechanics.
- Off-screen tracking arrows point to current locations of colonized planets & moons.

### v1.1.1 — Mobile Support
- Virtual joystick (bottom-left HUD) for steering & thrust on touch screens.
- Contextual `DOCK` / `BRAKE` / `MAP` action buttons added to the bottom-right layout.
- Planet panel slides up dynamically from bottom layout on small screen dimensions.
- Touch-specific controls explicitly mapped on the primary title screen for mobile players.

### v1.1 — Modules
- Farm modules generate food passively (6s build time mechanics).
- Fuel generator modules refuel ship when docked safely (8s build time mechanics).
- Module construction progress visualized via a dedicated progress bar in the planet panel.
- Pulsing yellow dots display above planets while a module is under active construction.

### v1.0 — Launch
- Arcade ship physics framework — thrust, rotate, and manual braking.
- Planet colonization engine with modular slot-based mechanics.
- Larger planets feature more operational slots (up to 5 maximum).
- Auto-save engine pushes state to browser `localStorage` every 5 seconds.
- Animated twinkling star field background environment mapping.
