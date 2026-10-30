---
tags:
  - fork-ledger
  - cli
---

# NOTES.md — cli — the repo decision log

One card per decision/commit, oldest first — append new cards at the bottom.
Cross-repo cards live in the global `../NOTES.md`; empty slots stay bare, no filler.

## 2026-10-29 10:26
* **What:** P0-3 audit: cli is Python (src/caelestia), not Go; `caelestia update` defaults to caelestia-dots/caelestia@main, overridable via ~/.config/caelestia/cli.json "dots"
* **Why:** feeds R-002
* **Taught:** config escape hatch
