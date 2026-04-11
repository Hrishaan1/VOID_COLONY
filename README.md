# VOID COLONY — Space Colonization Simulator
A high-fidelity, browser-based space exploration and economic simulation built with vanilla JavaScript and HTML5 Canvas.

## 🌌 Overview
In VOID COLONY, you take command of a lone colony ship. Your mission is to expand across a procedurally generated solar system, establishing outposts on planets and moons while managing critical resources. The game features a "living" solar system where every celestial body follows real-time orbital paths.

## 🚀 Key Features
- Procedural Universe: Every new game generates a unique star system with custom planet palettes, cloud formations, and moon systems.
- Orbital Mechanics: Physics-based flight including thrust, friction, and orbital co-movement (the ship drifts naturally with a planet's gravity when nearby).
- Module System: * Farms: Produce food (requires proximity to harvest).
- Fuel Generators: Refuel your ship at the cost of food modules.
- Dynamic Economy: A built-in market where food prices fluctuate every 60 seconds. Use the HUD slider to manage your sell-ratio.
- Cross-Platform: Full keyboard support (WASD) and a custom-coded virtual joystick for mobile/touch devices.
- Data Persistence: Automatic save/load functionality using localStorage.

## 🕹️ Controls
| Action | Keyboard| Touch |
| ---- | ---- | ---- | 
| Thrust | `W` / `Up` | Joystick Up |
| Rotate | `A` / `D` | Joystick Left/Right | 
| Brake | `S` / `Down` | Brake Button |
| Interact | `E` | Dock Button |
| Map | `M` | Map icon |
| Pause | `P` | Pause Icon |

## 🛠️ Technical Implementation
- Double Canvas Rendering: Uses a background canvas for static starfields and a foreground canvas for high-frequency physics updates.
- State Management: Centralized state object for easy serialization and save-game handling.
- Math-Heavy Logic: Implements trigonometry for orbital positioning ($$x=cos(θ) × radius$$) and collision detection with bounce physics.

## 📜 License
This project is open-source. Feel free to fork, modify, and expand your own galaxy!
