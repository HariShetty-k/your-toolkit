# Changelog

Versions of the `your-toolkit` plugin (`.claude-plugin/plugin.json`).

## 1.4.2 — 2026-10-06

- `superpowers` stays in the starter settings as the debugging and quality
  plugin. The starter `CLAUDE.md` and `AGENTS.md` now send feature planning to
  the `spec` skill and debugging, tests and verification to `superpowers`, so
  the two don't compete.

## 1.4.1 — 2026-10-06

- Removed the toolkit's own license; the repo is all rights reserved.
- Kept VoltAgent's MIT notice with the design catalog, as their license requires.
- Starter settings no longer enable `frontend-design`: it duplicated the
  `design` skill and pushed its own styling over `DESIGN.md`.
- Removed the catalog's manual "How to Use" steps, which repeated the `design` skill.

## 1.4.0 — 2026-10-06

- New `setup` skill: copies the starter files into any new or existing repo,
  merging `.claude/settings.json` and never overwriting existing docs.
- Starter files moved from the repo root to `templates/project/`, so the root
  only holds the toolkit's own files. The GitHub "Use this template" flow is
  replaced by the `setup` skill.
- Added this changelog and maintainer notes in `AGENTS.md`.
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
