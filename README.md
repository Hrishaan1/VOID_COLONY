# VOID COLONY — Space Combat & Colonization Simulator

A high-fidelity, browser-based space exploration, economic, and combat simulation built with vanilla JavaScript and HTML5 Canvas.

## 🌌 Overview
In **VOID COLONY**, you command a lone colony ship in a "living" solar system. Balance the high-stakes economy of fuel and food while defending your territory from enemy raiders that actively seek to capture your planets and destroy your modules.

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

## 📜 License
Open-source under the MIT License. Contributions and forks are welcome!
