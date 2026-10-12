# FirstAICode

A small collection of self-contained browser games. Open a game's HTML file directly in a modern browser; no installation, build step, or server is required.

## Games

### Memory Game

Match pairs on a 4x4 or 6x6 board, track your time and moves, and try to beat your best scores. Includes a persistent light/dark theme toggle and keyboard controls.

- [Play Memory Game](memory-game.html)
- [Memory Game dark theme PRD](PRD_dark_theme.md)
- Best scores are saved locally in your browser under `memoryGameScores`.

### Snake

Guide the snake to collect food, grow, and avoid walls and its own body. Choose Slow, Medium, or High speed; pause, resume, or restart at any time.

- [Play Snake](snake-game.html)
- [Snake game PRD](PRD_snake_game.md)
- Use arrow keys or WASD to steer, Space to pause/resume, and R to restart. On-screen direction buttons and swipe controls are also available.
- Best score is saved locally in your browser under `snakeGameBestScore`.

## Run Locally

Open either HTML file directly. To serve the files locally instead, run:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000/` and choose a game.

Scores and preferences are stored in the current browser and are not synchronized across devices. The games have no external runtime dependencies.
