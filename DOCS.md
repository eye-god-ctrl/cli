# DOCS.md — the story of the cli fork
Non-coder-friendly first, "For devs" inside each chapter. See ../playbooks/docs-fold.md.
`Last folded: 2026-10-30 22:54 — upstream sync`

## **Chapter 1 — Upstream sync (2026-10-30)**
**What it is.** The command-line tool was brought back level with upstream: 18 new upstream commits (11 files) were merged into this repo's `custom` branch. The fork adds no code of its own yet — only documentation — but the tool underneath gained the ability to handle video wallpapers.

**Why it exists.** The cli is the half of Caelestia that the desktop shell calls out to. Upstream taught the shell to render video wallpapers (shell #2167); the cli had to learn to **accept** them — recognise `.mp4` and friends as wallpapers, and generate a thumbnail from the first frame using `ffmpeg`. Without this half, `caelestia wallpaper -f ~/Videos/x.mp4` would simply refuse. The two halves are a package: they shipped in the same sync.

**How it works (non-coder version).** `main` stays a pure copy of upstream and is never edited; `custom` is the branch you actually use. The sync slid `main` forward, merged it into `custom` as one labelled commit, then pushed it to GitHub.

**For devs.** Merge commit `26dc5ec`; upstream range `4eac37f..f660eb88d`. In `src/caelestia/utils/wallpaper.py`: `VIDEO_EXTENSIONS = [".mp4", ".mkv", ".webm", ".mov", ".avi"]`, `is_video()`, `is_animated()` (`.gif` + video), `extract_first_frame()` shelling out to `ffmpeg`, and a video-aware `set_wallpaper` path (#183). `build(nix)` now sets the version from an env var and adds `ffmpeg` to the Nix build arguments (#185). Also: Hyprland socket responses are decoded only after all chunks are joined (#142); colour scoring no longer recurses forever on a fully black image (#135); the Discord template uses the Caelestia logo (#153). New dependency: `ffmpeg` (already listed in the README's dependency block).

**How it differs from upstream.** Only the five fork documentation files (`AGENTS.md`, `CLAUDE.md`, `DOCS.md`, `NOTES.md`, `VERSIONS.md`). Upstream touches none of them, so future syncs should stay conflict-free.

**Risks / how to undo.** The cli now shells out to `ffmpeg` for video wallpapers — on a machine without `ffmpeg`, setting a video wallpaper fails (still images are unaffected). Undo is `git revert -m 1 26dc5ec`, a normal commit; history is never rewritten. The cli has no test suite configured, so upstream's own testing is the only net — which is why the in-VM dry run matters.

**What was verified, and what wasn't.** Verified: fast-forward clean, `git merge-tree` conflict preview clean, `custom` contains upstream's tip, `diff main..custom` shows only the five doc files, zero conflict markers, local == GitHub. **Not verified:** that `ffmpeg` is installed, that a video wallpaper can actually be set, that thumbnails render — all HUMAN-ONLY in the VM (`playbooks/vm-verify.md`), still open as P0-6.

**You learned:** *merge-base drift*, *catch-up merge*, *upstream-first porting* (see the global Toolbox in `../DOCS.md`).
