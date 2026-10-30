# AGENTS.md — cli (thin)
Read ../AGENTS.md first — it governs everything. This file only adds repo-specific facts.
Repo: cli | upstream: caelestia-dots/cli | origin: eye-god-ctrl/cli
Role verified (P0-3, 2026-10-29): the caelestia command-line tool — **Python** (`src/caelestia/`), not Go.
Branches: `main` mirror (never commit) · `custom` (only via Merge Gate) · `feat/*`, `fix/*`.
Docs here (on `custom` only): NOTES.md, VERSIONS.md, DOCS.md, README.md "Fork notice".
Build/run (from upstream README, cited): AUR `caelestia-cli` stable / `caelestia-cli-git` (README.md:24-29) · Nix `nix run github:caelestia-dots/cli` (README.md:33-37) · manual: install python-build/installer/hatch/hatch-vcs then `python -m build --wheel` + `python -m installer dist/*.whl` (README.md:68-88). No test suite configured in pyproject.toml (checked 2026-10-29).
Repo gotchas: `caelestia update` defaults to upstream dots `caelestia-dots/caelestia@main` (utils/dots/source.py:18-19) — overridable via `~/.config/caelestia/cli.json` `"dots": {"url": …, "branch": …}`; update also runs a full AUR system update (subcommands/update.py:31).
