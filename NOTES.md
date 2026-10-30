---
tags:
  - fork-ledger
  - cli
---

# NOTES.md — cli — the repo decision log

One bullet per decision/commit, oldest first. Cross-repo lines live in the global `../NOTES.md`.
Format: `- **YYYY-MM-DD HH:MM · what** — *why*` · tag lessons with `[taught: concept]`.

---

- **2026-10-29 10:26 · P0-3 audit** — cli is Python (src/caelestia), not Go; `caelestia update` defaults to caelestia-dots/caelestia@main, overridable via `~/.config/caelestia/cli.json` "dots" — *feeds R-002* [taught: config escape hatch]
