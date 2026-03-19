# Testing the Battleship Game

## Local Setup

1. Serve the repo root with any static HTTP server:
   ```bash
   python3 -m http.server 8080
   ```
2. Open `http://localhost:8080` in Chrome

## Testing Workflow

### Difficulty Selection
- Page loads to difficulty screen with Easy / Medium / Hard buttons
- Default Medium has a yellow ring highlight
- Clicking a button transitions to the game screen; verify "Difficulty: X" in the status bar

### Ship Placement
- Ships are placed in order: Carrier(5), Battleship(4), Cruiser(3), Submarine(3), Destroyer(2)
- Hover over player grid cells to see green (valid) or red (invalid) preview
- Press **R** or click **Rotate (R)** button to toggle horizontal/vertical
- The label below the grids updates to show current ship and orientation
- Clicking on an invalid position (overlap or off-board) does nothing — placement label stays the same
- After placing all 5 ships, phase transitions to battle: green message, timer starts, placement controls hide

### Battle Phase
- Click cells on the **Opponent Waters** grid to fire
- Hit = red cell, Miss = blue cell, Sunk = all ship cells turn orange
- Shot counter increments on each player shot
- AI responds after ~600ms delay with its own shot on the player grid
- Ship status lists update in real time; sunk ships get red strikethrough

### Win/Loss Conditions
- **Win**: Green message "You Win! X shots in M:SS", confetti animation, Play Again button
- **Loss**: Red message "You Lost! AI sank your fleet in M:SS.", Play Again button (no confetti)
- Play Again returns to difficulty selection; all state resets

### Accelerated Testing with DevTools
- Open DevTools Console (F12) during battle phase
- Get enemy ship positions:
  ```js
  opponentBoard.ships.map(s => s.name + ': ' + s.cells.map(c => String.fromCharCode(65+c.r) + (c.c+1)).join(','))
  ```
- This lets you target specific cells to quickly test hit/sunk/win flows

### Sound Testing
- Sounds may be blocked on first page load due to browser autoplay policy
- After the first user click, sounds should play on: hit, miss, sunk, win, lose
- Audio elements are in the HTML: `#hit-sound`, `#miss-sound`, `#sunk-sound`, `#win-sound`, `#lose-sound`

## Key Files
- `index.html` — Single-file game (HTML + CSS + JS, ~750 lines)
- `sounds/` — Audio files (hit.mp3, miss.wav, sunk.wav, win.mp3, loss.wav)

## Devin Secrets Needed
None — this is a static HTML game with no authentication or API keys.
