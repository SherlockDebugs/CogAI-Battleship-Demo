# Bug Report & Testing Summary

## Testing Performed

- **Difficulty screen**: All three buttons (Easy, Medium, Hard) render correctly. Default Medium is highlighted. Clicking any button transitions to the game board.
- **Ship placement**: Tested placing all 5 ships in both horizontal and vertical orientations. Green/red preview renders correctly. Overlapping placements are properly rejected. Off-board placements show red preview and are rejected on click.
- **Battle phase**: Timer starts after all ships are placed. Shot counter increments on each player shot. Clicking already-fired cells is ignored (no double-fire).
- **Hit/Miss/Sunk visuals**: Hits display red, misses display blue, sunk ships turn orange with all cells revealed. CSS animations (flash, ripple, pulse) trigger correctly.
- **AI turns**: AI fires after each player shot with a short delay. AI shots correctly mark player board cells. AI respects hunt/direction logic on Medium and Hard.
- **Ship status lists**: Both player and enemy ship lists update in real time. Sunk ships are crossed out with red styling.
- **Win/Lose conditions**: Game correctly detects when all ships are sunk. Win triggers confetti animation and victory sound. Loss triggers defeat message and loss sound.
- **Play Again**: Returns to difficulty selection screen. New game initializes cleanly with fresh boards and timer reset.
- **Sound effects**: All 5 sound types (hit, miss, sunk, win, lose) play correctly when triggered. Autoplay policy errors are caught silently.

## Bugs Found & Fixed

- **Sounds folder casing**: Original folder was named `Sounds/` (capital S) but audio elements referenced `./sounds/` (lowercase). Fixed by renaming folder to `sounds/`.

## Known Limitations

- **Browser autoplay policy**: Some browsers may block sound on the first interaction. Sounds will play after the user's first click on the page.
- **Mobile layout**: The game is playable on mobile but optimized for desktop viewport widths (two grids side by side).

## Status

No major issues after full playtests. Game is stable and fully functional across all difficulty levels.
