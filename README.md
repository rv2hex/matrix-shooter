# MATRIX_DEFENDER // rv2hex

A single-file Matrix-themed space shooter. No build step, no dependencies —
just open it in a browser. Defend the grid against falling malware.

## Play

Open `index.html` in any modern browser, or serve the folder:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Controls

| Input | Action |
|---|---|
| `←` / `→` or `A` / `D` | Move ship |
| `Space` / `↑` / `W` | Shoot |
| `Space` (on game-over screen) | Reboot system (restart) |

## Rules

- Enemies (`VIRUS`, `CORRUPT`, `0xERR`, `MALWARE`, `BUG`) rain from the top,
  each takes **2 hits**, kill = **+100 score**.
- Anything that slips past the bottom line costs **15% system integrity**.
- At 0% integrity: `CRITICAL_SYSTEM_FAILURE`. Press Space to reboot.

## Structure

```
index.html   everything: Matrix-rain canvas backdrop, HUD
             (score / status / integrity), scanline overlay,
             game loop (player, bullets, enemies, particles)
```

Canvas 2D only; game state resets on page reload (no persistence).
