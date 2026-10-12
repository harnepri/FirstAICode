# PRD: Dark Theme for Memory Game

## Summary

Add an optional dark theme to the existing standalone Memory Game. Players can switch between light and dark appearances while playing. The selected theme should persist in the current browser without changing game rules, active game state, or saved scores.

## Background

The application is a dependency-free HTML, CSS, and JavaScript game in `memory-game.html`. It currently has a light appearance. A few colors are defined as CSS custom properties, while controls, the score list, and the win dialog use hard-coded light backgrounds. Game state and the best-five score list are managed separately; scores are stored in `localStorage` under `memoryGameScores`.

## Goals

- Offer clear light and dark themes across the complete game interface.
- Make the theme easy to switch using mouse, touch, and keyboard.
- Remember a player's choice across reloads in the same browser.
- Preserve existing gameplay, accessibility, responsive behavior, and score data.
- Keep the application self-contained, with no new runtime dependencies.

## Non-Goals

- Redesign the game or change its layout, rules, grid sizes, scoring, or animations.
- Add accounts, server-side preferences, or cross-device synchronization.
- Change, clear, migrate, or reorder saved scores as part of theme selection.
- Add additional color themes beyond light and dark.

## User Stories

- As a player, I can switch to a dark appearance when it is more comfortable to play.
- As a player, I can switch back to the existing light appearance at any time.
- As a player, my theme choice remains selected after I reload or reopen the game in the same browser.
- As a player, changing the theme during a game does not interrupt or restart that game.

## Requirements

### Theme selection and persistence

1. Add a clearly labeled, keyboard-accessible theme control to the game interface. Its label or accessible name must communicate the action or current theme, such as “Dark theme” / “Light theme.”
2. The control must switch immediately between light and dark appearances without reloading the page.
3. Keep the current light appearance as the initial default when no saved preference exists. This avoids changing the established first-visit experience.
4. Save the selected theme using a dedicated `localStorage` key that is separate from `memoryGameScores`.
5. Restore a valid saved theme before the first visible render where practical. If storage is unavailable or contains an invalid value, use the light theme and keep the game usable.
6. Changing themes must not reset the board, timer, moves, rating, selected grid size, or win dialog state.

### Visual coverage

1. Apply each theme consistently to the page background and text, header, statistics panel, grid-size controls, card faces and backs, best-score section, win dialog, and focus indicators.
2. Use shared CSS custom properties (or an equivalent centralized styling approach) so all themed surfaces use a coherent palette. Avoid leaving hard-coded light surfaces that become glaring against the dark page.
3. Maintain readable contrast for text, card symbols, button states, focus outlines, and status information in both themes.
4. Preserve the existing card-flip appearance, responsive grid behavior, spacing, and overall structure.
5. Provide visible hover, focus, active, and selected states for the theme control and existing buttons in both themes.

### Accessibility and compatibility

1. The theme control must work with keyboard navigation and expose its purpose and current state to assistive technology.
2. Do not communicate theme or control state through color alone.
3. Preserve existing keyboard card activation and the current ARIA behavior of the game grid and statistics.
4. Keep the game functional in modern browsers that support the existing HTML, CSS, JavaScript, and `localStorage` features. Do not introduce a build step or external dependency.

## Acceptance Criteria

- With no saved theme preference, opening the game shows the current light theme.
- Activating the theme control switches every listed interface surface to a legible dark palette; activating it again restores light mode.
- The selected theme is restored after a page reload in the same browser.
- A theme change during an unfinished game preserves the same cards, matches, moves, timer value and running state, rating, and selected grid size.
- A theme change while the win dialog is open leaves the dialog and final statistics intact.
- Existing best scores remain unchanged and visible in either theme; the theme preference does not overwrite the `memoryGameScores` entry.
- Both 4x4 and 6x6 boards remain usable at desktop and mobile widths.
- Cards remain operable with mouse, Enter, and Space; the theme control is reachable and operable by keyboard.
- Focus, button, text, card, score, and dialog content remain discernible in both themes.
- The game still opens directly from `memory-game.html` without a server, build, or installed dependency.

## Suggested Implementation Notes

- Keep the change within the existing single-file application unless implementation reveals a concrete reason otherwise.
- Define light and dark values in CSS custom properties, selected through a root attribute or class. Replace themed hard-coded surface and state colors with those tokens.
- Keep theme initialization and persistence independent from game initialization and score rendering. A theme toggle should update presentation only.
- Use a dedicated storage key such as `memoryGameTheme`; do not reuse or modify `memoryGameScores`.
- Validate the selected theme value before applying it, and gracefully fall back to light mode if browser storage cannot be read or written.

## Verification Plan

1. Open `memory-game.html` with no stored theme value and confirm the light theme is unchanged.
2. Switch to dark mode and inspect the entire page, including both grid sizes, matched and unmatched cards, focus states, score list, and win dialog.
3. Reload and confirm the selected theme persists; switch back to light mode and confirm that choice also persists.
4. Start a game, flip cards, and change themes while the timer is running. Confirm the board and all game statistics continue unchanged.
5. Complete a game in each theme and confirm the win flow and best-score list still work.
6. Repeat key controls using keyboard only and check the layout at a narrow mobile viewport.
7. Compare the `memoryGameScores` data before and after theme changes to verify it is unaffected.

## Risks and Mitigations

| Risk | Mitigation |
| --- | --- |
| A missed hard-coded color leaves a bright surface in dark mode. | Audit every visible surface and interaction state in both themes. |
| Theme initialization accidentally resets the game. | Keep theme setup separate from `initializeGrid()` and verify a mid-game switch. |
| Theme data overwrites or corrupts scores. | Use a dedicated storage key and verify existing score data remains intact. |
| Dark colors reduce readability or hide focus. | Check text, controls, card faces, and focus indicators in both themes. |
| Browser storage is blocked or malformed. | Fall back to light mode without preventing the game from starting. |

## Release Decision

The feature is ready when all acceptance criteria pass in a browser and existing gameplay and score persistence remain unchanged. The game owner will perform the final hands-on play-through after implementation.