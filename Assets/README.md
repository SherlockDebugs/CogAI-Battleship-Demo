# Ship Assets

Pixel art naval ship sprites from the [Sea Warfare set on OpenGameArt](https://opengameart.org/), top-down naval view with transparent backgrounds.

## Ship-to-Grid Mapping

| Grid Spaces | Ship Name  | Player File              | Enemy File              |
|-------------|-----------|--------------------------|-------------------------|
| 5           | Battleship | `player_Battleship.png`  | `enemy_Battleship.png`  |
| 4           | Carrier    | `player_Carrier.png`     | `enemy_Carrier.png`     |
| 3           | Submarine  | `player_Submarine.png`   | `enemy_Submarine.png`   |
| 2           | Patrol     | `player_Patrol.png`      | `enemy_Patrol.png`      |

## Usage in Game Code

Use `player_` prefixed files for the user's fleet and `enemy_` prefixed files for the AI opponent's fleet.

```js
// Example: loading a player ship sprite
const img = new Image();
img.src = 'Assets/player_Battleship.png'; // 5-space ship

// Example: loading an enemy ship sprite
const enemyImg = new Image();
enemyImg.src = 'Assets/enemy_Carrier.png'; // 4-space ship
```

> **Note:** The folder is capitalized as `Assets/` — use this exact casing in file paths.

## Color Palettes

**Original (neutral):** Grey/steel military palette — used as base for recoloring.

**Player variants (friendly navy):**
- Main hull: cool steel blue-grey (`#5a7a9a`)
- Highlights: light cyan / white-blue (`#b0d0ff`, `#e0f0ff`)
- Shadows: darker blue-grey (`#3a4a6a`)

**Enemy variants (menacing):**
- Main hull: dark charcoal with red tint (`#3a2a2a`, `#4a1a1a`)
- Accents: blood red / dark orange-red (`#8b0000`, `#cc3300`)
- Shadows: near-black (`#1a1a1a`)

## File Structure

```
Assets/
├── Battleship/Battleship.png    # Original (neutral)
├── Carrier/Carrier.png          # Original (neutral)
├── Submarine/Submarine.png      # Original (neutral)
├── PatrolBoat/Patrol.png        # Original (neutral)
├── player_Battleship.png        # Player recolor (blue)
├── player_Carrier.png           # Player recolor (blue)
├── player_Submarine.png         # Player recolor (blue)
├── player_Patrol.png            # Player recolor (blue)
├── enemy_Battleship.png         # Enemy recolor (red)
├── enemy_Carrier.png            # Enemy recolor (red)
├── enemy_Submarine.png          # Enemy recolor (red)
├── enemy_Patrol.png             # Enemy recolor (red)
└── README.md                    # This file
```
