# Browser Games

Two single-file vanilla HTML/JS games. No build tools, dependencies, tests, or lint config.

## Running

Open the `.html` files directly in a browser. No server required, but a VM without a GUI needs an HTTP server:

```bash
python3 -m http.server 80 --directory /root
# play at http://<host>/shooter.html or /tic-tac-toe.html
```

For public access from a headless VM, expose via an SSH reverse tunnel (e.g. `localhost.run`). Free tunnels are short-lived and the URL changes on each reconnect — restart the tunnel to get a new URL.

## Repo layout

- `shooter.html` — arena shooter
- `tic-tac-toe.html` — tic-tac-toe
- `AGENTS.md` — this file

Git is initialized in `/root` (not a project subdir). Push target: `github.com/vutukurivishal07-byte/vishal-AI-TESTING` (branch `main`, SSH auth).

## Conventions

- Pure vanilla JS — no frameworks, modules, or bundlers. Each game is fully self-contained in one file.
- Game state is plain top-level variables mutated in a `requestAnimationFrame` loop.
- `shooter.html`: state in `player`, `score`, `wave`, `gameOver`; arrays `bullets`, `enemyBullets`, `enemies`, `particles`, `trails`; mouse steers + auto-fires toward cursor; HP with invulnerability frames; waves escalate over time.
- `tic-tac-toe.html`: state in `board`, `currentPlayer`, `gameOver`, `scores`; win detection via 8 hardcoded patterns on a flat 9-element array; scores persist across rounds within the session (cleared on reload).
- No persistence (localStorage/cookies) — all state resets on reload.

## Gotchas

- Do not commit local/sensitive dirs from `/root`. The `.gitignore` excludes `.ssh/`, `.config/`, `.cache/`, `.claude/`, `.vscode-server/`, `.opencode/`, `.local/`, `.npm/`, shell history, and `node_modules/`. Keep it that way.
- There is no test suite, linter, or typechecker — verification is manual (open in browser).