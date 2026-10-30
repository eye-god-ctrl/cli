---
tags:
  - fork-ledger
  - cli
---

# NOTES.md — cli — the repo decision log

One row per decision/commit, oldest first — append new rows at the bottom.
Cross-repo lines live in the global `../NOTES.md`; escape any literal pipe in content as `\|`.

| When | What | Why | Taught |
|---|---|---|---|
| 2026-10-29 10:26 | P0-3 audit: cli is Python (src/caelestia), not Go; `caelestia update` defaults to caelestia-dots/caelestia@main, overridable via ~/.config/caelestia/cli.json "dots" | feeds R-002 | [taught: config escape hatch] |
