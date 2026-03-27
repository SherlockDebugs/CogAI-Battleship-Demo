# Battleship

A complete browser-based Battleship game — play against a smart AI opponent with three difficulty levels.

**[Play Live](https://sherlockdebugs.github.io/CogAI-Battleship-Demo/)** (if hosted via GitHub Pages)

---

## How to Play

1. **Open `index.html`** (2D) or **`index-3d.html`** (3D) in any modern browser (or serve via any static file server).
2. **Select Difficulty** — Easy, Medium, or Hard (default: Medium).
3. **Place Your Ships** — Click cells on "Your Fleet" grid to place each ship.
   - Press **R** or click the **Rotate** button to toggle between horizontal and vertical placement.
   - Green preview = valid placement; red preview = invalid (overlap or off-board).
   - Ships are placed in order: Carrier (5), Battleship (4), Cruiser (3), Submarine (3), Destroyer (2).
4. **Battle!** — Click cells on "Opponent Waters" to fire.
   - **Red** = Hit, **Blue** = Miss, **Orange** = Sunk (full ship revealed).
   - The AI fires back after each of your shots.
5. **Win** by sinking all five enemy ships before the AI sinks yours.

---

## Features

- **Two 10x10 grids** with row (A-J) and column (1-10) labels
- **5 ships**: Carrier (5), Battleship (4), Cruiser (3), Submarine (3), Destroyer (2)
- **Manual ship placement** with rotation, live preview, and overlap/boundary validation
- **AI with 3 difficulty levels**:
  - **Easy** — Pure random targeting
  - **Medium** — Hunt mode (targets adjacent cells after a hit)
  - **Hard** — Hunt + directional continuation on hit patterns
- **Sound effects** for hit, miss, sunk, win, and loss events
- **Shot counter** and **elapsed timer**
- **Ship status lists** for both fleets (crossed out when sunk)
- **CSS animations** (2D) / **3D particle effects** (3D) — explosions, water splashes, fire on damaged ships
- **Confetti** on victory (CSS in 2D, 3D particles in 3D version)
- **3D version** with animated ocean water shader, orbit camera controls, ship sinking animations
- **Play Again** button to restart with a new difficulty

---

## Tech Stack

- **Single file**: `index.html` (2D) / `index-3d.html` (3D) — no build step required
- **Tailwind CSS** via CDN for styling
- **Vanilla JavaScript** — modular classes (`Ship`, `Board`, `AI`)
- **HTML5 Audio** for sound effects
- **Three.js** via CDN for 3D version (scene, lighting, shaders, raycasting)

---

## Project Structure

```
├── index.html          # Complete 2D game (HTML + CSS + JS)
├── index-3d.html       # Complete 3D game (Three.js + HTML overlay)
├── sounds/
│   ├── hit.mp3         # Hit sound effect
│   ├── miss.wav        # Miss sound effect
│   ├── sunk.wav        # Ship sunk sound effect
│   ├── win.mp3         # Victory sound effect
│   └── loss.wav        # Defeat sound effect
├── README.md           # This file
└── BUGS.md             # Testing notes and bug log
```

---

## Sound Credits

All sounds are **CC0 (public domain)** from [Freesound.org](https://freesound.org/).

---

## Running Locally

```bash
# Any static file server works:
python3 -m http.server 8080
# Then open http://localhost:8080 (2D) or http://localhost:8080/index-3d.html (3D)
```

Or simply open `index.html` directly in your browser (sounds may require a server due to browser autoplay policies).
