# PRD: Snake Game

## Summary

Provide a classic Snake arcade game as a single, self-contained HTML file. Players steer a snake around a grid, collect food to grow and score, and avoid walls and their own body. The game should open directly in a modern browser without a build step or external dependencies.

## Goals

- Deliver a complete, immediately playable Snake game in `snake-game.html`.
- Support keyboard, touch-button, and swipe controls.
- Make score, best score, speed, pause, restart, win, and loss states clear.
- Preserve a player's best score locally in the current browser.
- Keep the board and controls usable at desktop and mobile sizes.
- Provide accessible labels, visible keyboard focus, and reduced-motion support.

## Non-Goals

- Add accounts, online leaderboards, multiplayer, or server-side storage.
- Add external libraries, image assets, audio dependencies, or a build pipeline.
- Reproduce platform-specific Snake variants or add configurable board dimensions and alternate rule variants.

## User Stories

- As a player, I can start and steer Snake with the keyboard or touch controls.
- As a player, I can collect food, see my score increase, and see the game speed up.
- As a player, I can pause, resume, or restart at any time.
- As a player, I can choose Slow, Medium, or High movement speed and change it during a run.
- As a player, I can see my best score again after reopening the game in the same browser.
- As a player, I receive a clear game-over or board-cleared state and can play again.

## Requirements

### Gameplay

1. Render a square board with a 24-by-24 logical grid and a snake that advances at a steady interval.
2. Start the snake with multiple segments and an initial direction. The player must be able to change direction without allowing an immediate reversal into the snake's body.
3. Place one food item at a time on an unoccupied grid cell. Eating food grows the snake and adds 10 points.
4. Increase movement speed at score milestones, while enforcing a minimum tick interval so the game remains playable.
5. A collision with a board boundary or the snake's body ends the game. Filling every board cell completes the game with a win state.
6. Pause must stop movement; resume must continue from the same board and score. Restart must return to a fresh board and zero current score.
7. After game over or a win, allow the player to start a new game.
8. Offer Slow, Medium, and High speed presets, with Medium selected by default. Each preset has a distinct initial speed and acceleration cap; score milestones continue to increase movement speed.
9. Changing the speed preset during play or while paused must preserve the current board, direction, and score, and take effect without restarting the game. Keep the selected preset when restarting a game in the same page session.

### Controls and accessibility

1. Support arrow keys and WASD for direction; Space pauses or resumes; R restarts.
2. Provide labeled on-screen direction buttons for touch and pointer input, plus swipe direction on the board.
3. Prevent page scrolling for game keys when those keys control active play, without blocking normal keyboard interaction with buttons.
4. Expose the current score and game status accessibly, label the game board and controls, and show a visible focus indicator.
5. Honor `prefers-reduced-motion` for interface transitions.

### Persistence and compatibility

1. Save the best score under a dedicated local-storage key, separate from other games' data.
2. If browser storage is unavailable or invalid, the game must still load and remain playable with a session-only best score.
3. Resize the rendered canvas to fit its container and account for device pixel ratio without changing the logical grid.
4. Keep all markup, styles, and game code in `snake-game.html`; do not require a server, build, or external dependency.

## Acceptance Criteria

- Opening `snake-game.html` directly shows a ready board and working controls.
- Play starts movement; arrow/WASD and touch controls steer without instant reversal; swipe changes direction.
- Eating food increases the score by 10 and increases snake length; speed advances at milestones.
- Wall and self-collisions stop play and show a game-over state.
- Filling the board ends with a win state without attempting to place food on an occupied board.
- Pause/resume preserves the current game; restart resets the current game.
- Slow, Medium, and High are selectable and expose the selected state; Medium is the default.
- Changing speed during a run does not reset game progress, and the selected mode remains active after restart.
- The best score survives reloads and remains independent of Memory Game score storage.
- Keyboard focus and accessible names are present, and reduced-motion preference is respected.
- The board remains square and usable on narrow mobile and desktop viewports.
- No external resources, dependencies, or build steps are required.

## Verification Plan

1. Open the HTML file and verify initial render, board sizing, status, and score displays.
2. Start, steer, pause, resume, and restart using keyboard controls.
3. Steer into food and confirm score, growth, and speed changes.
4. Use touch-direction buttons and swipe input; check a narrow viewport.
5. Verify wall and self-collision game-over states, then restart.
6. Verify high-score persistence after reload and confirm the separate Memory Game score key is untouched.
7. Confirm the full-board completion condition exits cleanly without an infinite food-placement loop.

## Release Decision

The game is ready when all acceptance criteria pass in a modern browser and it remains playable when local storage is blocked. The owner will perform the final hands-on play-through.