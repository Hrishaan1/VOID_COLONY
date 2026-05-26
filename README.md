# VOID COLONY — Space Combat & Colonization Simulator

A high-fidelity, browser-based space exploration, economic, and combat simulation built with vanilla JavaScript and HTML5 Canvas.

## 🌌 Overview
In **VOID COLONY**, you command a lone colony ship in a dynamic solar system. Balance the high-stakes economy of fuel and food while defending your territory from enemy raiders that actively seek to capture your planets and destroy your modules.

## ⚔️ Combat & Defense Features (New!)
* **Laser Weaponry:** Engage enemies with high-velocity cyan laser bolts (SPACE or Mouse Click). Includes a 220ms cooldown system for balanced firing.
* **Enemy Raider AI:** Raiders spawn every 45 seconds, roaming the system to capture planets. They are peaceful unless provoked or unless you attempt to reclaim a stolen colony.
* **Mouse Aim Mode:** Press `C` to toggle a precision targeting mode where the ship rotates to face your cursor, complete with a dotted targeting line and crosshair.
* **Hull Integrity:** Your ship features a persistent health bar. Take damage from enemy fire and benefit from a slow automatic regeneration (2 HP/sec).

## 📈 Economic & Planetary Simulation
* **Credits Economy:** Everything has a cost—from colonizing (20¢) to building specialized modules like Farms (50¢) or Fuel Generators (80¢).
* **Dynamic Food Market:** Food prices fluctuate every 60s. Use the HUD slider to set your "Sell Ratio" and automate your income based on market trends.
* **Solar Bonds:** A speculative mini-game where you can buy/sell bonds on a 30s volatility cycle to build your credit reserves.
* **Proximity Harvesting:** Farm modules require you to remain within a specific orbital range to successfully harvest resources.

## 🕹️ Controls
| Action | Keyboard | Mouse / Touch |
| :--- | :--- | :--- |
| **Thrust / Rotate** | `WASD` | Joystick (Mobile) |
| **Precision Aim** | `C` (Toggle) | Mouse Movement |
| **Fire Laser** | `Space` | Mouse Click / 🔴 Button |
| **Interact/Dock** | `E` | ⬡ DOCK Button |
| **Map** | `M` | 🗺 MAP Button |
| **Pause** | `P` | ⏸ PAUSE Button |

## 🛠️ Technical Implementation
* **State Persistence:** Automatically saves your fleet status, credits, and colony progress to `localStorage` every 5 seconds.
* **Procedural Systems:** Generates unique star systems with custom palettes, moon systems, and real-time orbital trigonometry.
* **Layered Rendering:** Uses dual HTML5 Canvases to handle high-frequency physics updates and background star-fields separately.

## Patch Notes
- **Future Update - Infinity**
    - A new passive type weapon that slows down all projectiles (to almost a full stop) when they are within a certain radius of you
        - The radius can be customized by the player, at the cost of higher cost to activate infinity with higher radii
    - Will cost 0.5 food per second that it is active
    - Pressing the shoot key will toggle infinity
- **Future Update - Baby Mode**
    - Much easier for people who are bad at the game
    - weapons instant kill raiders
    - black flash cannot be missed
    - Everything is cheaper, and you gain more money from all income sources 
- **v1.13 - Advanced Weapon Systems**
    - Added Gravity Well Launcher, Kinetic Flak Cannon, Solar Beam Overdrive, and Overcharged Shield Burst
    - Gravity wells pull nearby raiders into a temporary trap for easier Divergent Ram setups
    - Kinetic Flak Cannon fires short-range shrapnel with heavy knockback and unlocks after 3 active farms
    - Solar Beam Overdrive channels scaling damage while consuming food and locking ship movement
    - Overcharged Shield Burst clears enemy projectiles and disables nearby raider engines as a panic button
- **v1.12 - Leviathan Diplomacy**
    - Massive hostile Motherships can warp in an siphon nearby colony resources
    - added negotiation choices using Credits, Food, raider kills, or Laboratory Modules
    - Failed diplomacy starts component combat against the Leviathan engines and hangar
    - Quantam Rewind can revive a destroyed hull by sacrificing Credits or a building
- **v1.11 - Divergent Ram**
    - Added high-speed Collision Drive impacts against enemy raiders
    - Divergent Ram gives fuel, triggers hit stop, and vaporizes most raiders
    - Black Flash impacts distort targets with dark lightning and residual ship afterimages
    - Low-speed enemy collisions now punish the hull instead of becoming free damage
- **v1.10 - Trade Routes & Freighters**
    - Added purchasable AI freighters after you establish multiple colonies
    - Freighters haul food from farm colonies to the central hub for credits
    - Added escort missions when raiders ambush loaded freighters
    - Freighters are bulkier, slower variants of the player ship and appear on the map
- **v1.9 - Void Events**
    - Added random Solar Flares that temporarily disrupt the map or mouse aim
    - Added mineable passing comets wiht large credit rewards if you match velocity
    - Added rare paired wormholes that shortcut across distant solar orbits
- **v1.8 - Space Station Weapons**
    - Added a neutral space station near the system center
    - Dock at the station to buy and equip Pulse Wave or Railgun weapons
    - Pulse Wave deals short-range area damage; Railgun hits hard at long range and consumes fuel
- **v1.7 - Laboratory Research**
    - Added Laboratory modules and a permanent research tree
    - Research can improve engines, farm automation, shields, weapons, and max hull integrity
    - Shielding adds a passive recharging blue bar above hull integrity
- **v1.6 - Galaxy Starmap**
    - Added a draggable galaxy starmap with selectable nearby solar systems
    - Jump costs scale with each system's distance from the home system
    - Visited systems and systems with colonies are marked on the starmap
    - New nearby systems appear as you push deeper into the galaxy
- **v1.5.2.1 - Laser Firing Bug Fix**
    - Lasers weren't firing due to cooldown bug - has been fixed
- **v1.5.2 - Combat Rebalance**
    - Enemy ships now roam peacefully - they won't attack unprovoked
    - Enemy ships retaliate only if you shoot them first
    - Reclaiming an enemy planet triggers a retaliator ship to spawn
    - Ambient roamers drift between planets instead of idling
    - Hull integrity regenerates slowly over time (2 HP/sec)
- **v1.5.1 - Mouse Aim Mode**
    - Press C to toggle mouse aim - ship rotates to face your cursor
    - Click to fire in mouse aim mode (crosshair cursor shown)
    - Dotted targeting line drawn from ship to cursor
    - Thrust and brake controls unchanged in mouse mode
- **v1.5 - Enemy Raiders & Combat**
    - Enemy raider ships spawn every 45s (up to 5 at a time)
    - Enemies fly to planets, capture them, and destroy your modules
    - `SPACE` / 🔴 button fires cyan laser bolts at enemies
    - Destroying an enemy earns 40¢ bounty
    - Hull integrity bar added — take damage from enemy fire
    - Enemy-owned planets shown with red orbit ring
    - Reclaim captured planets for 80¢ from the planet panel
    - Enemy ships display HP bar and claim-progress bar in world
- **v1.4.1 - Solar Bonds**
    - Added Solar Bond market — buy & sell speculative bonds for profit
    - Bond prices fluctuate every 30 seconds with random surges & crashes
    - Portfolio view shows unrealised P&L, average buy price & price chart
    - Bond market accessible from Pause menu
- **v1.4 - Economy & Menus**
    - Added Credits currency — colonising costs 20¢, farms 50¢, fuel gens 80¢
    - Food Market with fluctuating prices (changes every 60s)
    - Food sell-ratio slider in HUD — split harvest between stock and credits
    -Fixed: sell ratio now correctly scales with number of farms
    - Pause menu (P key or ⏸ button) — pause, access markets, quit to title
    - Patch Notes screen accessible from pause & title screen
- **v1.3.2 - Farm Harvesting**
    - Farms only produce food when ship is within harvest range
    - Green dashed harvest-range ring shown around farm planets
    - Farm slot label shows live harvesting/idle status in planet panel
- **v1.3.1 - Moon Balance**
    - Moon sphere of influence reduced to 40% of planet proximity
    - Moon interact range halved — no longer hijacks planet approach
    - Moon orbits start further from planet surface (60px min)
    - Wider spacing between multiple moons around the same planet
- **v1.3 - Proximity & Resource Update**
    - Orbital co-movement: entering proximity locks ship to planet drift exactly
    - Planet collision physics — ship bounces off surfaces
    - Fuel gens cost 1 food/sec while actively refueling
    - Passive food consumption added (crew upkeep: 0.08/sec)
    - Food supply warning notification when reserves hit zero
- **v1.2.1 - Map Fixes**
    - Fixed map canvas only showing top strip — now fills panel correctly
    - Map reads wrapper dimensions after flex layout is applied
    - Map auto-fits to system scale on open via requestAnimationFrame
    - Mobile: map opens fullscreen; touch pan & pinch-zoom supported
- **v1.2 - Solar System & Map**
    - Full solar system layout — named star at centre, planets in orbital rings
    - Planets orbit in real time; moons orbit planets
    - Moons colonisable with 1 slot each; planet panel lists its moons
    - Floating draggable map (M) with scroll-to-zoom
    - Off-screen arrows point to colonised planets & moons
- **v1.1.1 - Mobile Support**
    - Virtual joystick (bottom-left) for steering & thrust on touch screens
    - `DOCK` / `BRAKE` / `MAP` action buttons (bottom-right)
    - Planet panel slides up from bottom on small screens
    - Touch-specific controls shown on title screen for mobile users
- **v1.1 - Modules**
    - Farm modules generate food passively (6s build time)
    - Fuel generator modules refuel ship when docked (8s build)
    - Module build shown as progress bar in planet panel
    - Pulsing yellow dots above planet while module is under construction
- **v1.0 - Launch**
    - Arcade ship controls — thrust, rotate, brake
    - Planet colonisation with slot-based module system
    - Larger planets have more slots (up to 5)
    - Auto-save to browser localStorage every 5 seconds


## 📜 License
Open-source under the MIT License. Contributions and forks are welcome!
