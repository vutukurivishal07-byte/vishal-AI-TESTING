# Tic-Tac-Toe

Single-file vanilla HTML/JS game (`tic-tac-toe.html`). No build tools, dependencies, or tests.

## Commands

There is no build/test/lint tooling. Open the file in a browser to run.

## Conventions

- Pure vanilla JS — no frameworks, modules, or bundlers.
- All code (HTML, CSS, JS) lives in one file.
- Game state is plain JS variables (`board`, `currentPlayer`, `gameOver`, `scores`).
- Win detection uses 8 hardcoded patterns on a flat 9-element array.
- Scores persist across games within the session (cleared on page reload).
