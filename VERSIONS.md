# VERSIONS.md — cli
## Upstream sync ledger
- Last synced upstream SHA: `f660eb88d` — date: 2026-10-30
- Adopted upstream commits: **all 18** (`4eac37f..f660eb88d`) — adopted wholesale via catch-up merge `26dc5ec`; per-commit verdicts in `../reports/sync-2026-10-30.md`
- Skipped upstream commits (with reason): _(none)_
## What each merge into custom brings
| Date | custom SHA | stack tag | What it brings |
|---|---|---|---|
| 2026-10-30 | `26dc5ec` | — | Upstream catch-up merge (`4eac37f` → `f660eb88d`, 18 commits / 11 files): **video wallpapers** — `VIDEO_EXTENSIONS` + `ffmpeg` first-frame thumbnails + video-aware `set_wallpaper` (#183), Nix build passes `ffmpeg` (#185), Hyprland socket chunk-join fix (#142), black-image colour-score recursion fix (#135). New dependency: `ffmpeg` |
