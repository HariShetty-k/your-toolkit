# Changelog

Versions of the `your-toolkit` plugin (`.claude-plugin/plugin.json`).

## 1.4.0 — 2026-10-06

- New `setup` skill: copies the starter files into any new or existing repo,
  merging `.claude/settings.json` and never overwriting existing docs.
- Starter files moved from the repo root to `templates/project/`, so the root
  only holds the toolkit's own files. The GitHub "Use this template" flow is
  replaced by the `setup` skill.
- Added `LICENSE` (MIT), this changelog, and maintainer notes in `AGENTS.md`.
- README reorganized: agent skills and design skills, quick start, repo layout.

## 1.3.0 — 2026-09-25

- Made the template development-ready: `CLAUDE.md`, `AGENTS.md`, `specs/` with
  spec, plan and task templates, and `.claude/settings.json` enabling this
  toolkit plus recommended official plugins.
- New `spec` skill.
- Doc templates renamed to uppercase; design catalog moved to `templates/`.

## 1.2.0 — 2026-09-25

- New `architecture` skill and `ARCHITECTURE.md` template.

## 1.1.0 — 2026-09-25

- New `motion` skill (Motion, formerly Framer Motion).
- The official 21st.dev plugin listed in the marketplace.

## 1.0.0 — 2026-09-25

- Packaged as a Claude Code plugin with the `product`, `design` and
  `user-journey` skills and their templates.
