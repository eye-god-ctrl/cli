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

## 2026-10-30 22:54
* **What:** Upstream sync — `main` fast-forwarded `4eac37f` → `f660eb88d` (18 commits / 11 files) and catch-up-merged into `custom` (`26dc5ec`, pushed). `custom` now differs from `main` only by our five doc files. Brings: **video wallpapers** — `VIDEO_EXTENSIONS` (`.mp4/.mkv/.webm/.mov/.avi`), `ffmpeg` first-frame thumbnails and video-aware `set_wallpaper` (#183), plus the Nix build now passing `ffmpeg` (#185)
* **Why:** the cli half of upstream's live-wallpaper feature — it ships together with shell #2167/#2180, so both halves had to land in the same sync. Needs `ffmpeg` installed on the host and in the VM golden image (owner-only install)
* **Taught:** merge-base drift, catch-up merge, upstream-first porting
