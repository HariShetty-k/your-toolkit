---
name: setup
description: Set up a new or existing repo with the toolkit's starter files (CLAUDE.md, AGENTS.md, PRODUCT.md, ARCHITECTURE.md, USER-JOURNEY.md, specs/, .claude/settings.json). Use when the user starts a new project or repo, asks to "set up", "bootstrap" or "initialize" a repo with their toolkit or template, or wants the standard docs added to a project.
---

# Setup

Copy the starter files from `../../templates/project/` (relative to this skill's directory) into the current project's root, so every repo starts with the same docs and agent instructions.

## Files

| Copy from `templates/project/` | To the project root | Purpose |
|---|---|---|
| `CLAUDE.md` | `CLAUDE.md` | Claude Code entry point; imports the docs below |
| `AGENTS.md` | `AGENTS.md` | Instructions for any AI coding tool |
| `PRODUCT.md` | `PRODUCT.md` | Blank, filled in by the `product` skill |
| `ARCHITECTURE.md` | `ARCHITECTURE.md` | Blank, filled in by the `architecture` skill |
| `USER-JOURNEY.md` | `USER-JOURNEY.md` | Blank, filled in by the `user-journey` skill |
| `specs/README.md`, `specs/_template/` | `specs/` | Spec, plan and task templates for the `spec` skill |
| `.claude/settings.json` | `.claude/settings.json` | Enables this toolkit's plugins and the recommended official plugins |

## Steps

1. Find the project root (the git root, or the current directory if it isn't a git repo).
2. List which of the files above already exist there. Never overwrite one silently:
   - **Docs that already exist** (`CLAUDE.md`, `AGENTS.md`, `PRODUCT.md`, …): keep the project's version and skip the template. If the project's `CLAUDE.md` doesn't import `AGENTS.md`, `PRODUCT.md` and `ARCHITECTURE.md`, offer to add those `@` lines.
   - **`.claude/settings.json` that already exists:** merge instead of replacing. Add the `extraKnownMarketplaces` and `enabledPlugins` entries that are missing, and keep everything else the project already has.
3. Copy the remaining files exactly as they are. Don't fill anything in yet.
4. If the project already has code, fill in the Commands table in `AGENTS.md` from its `package.json` scripts (or equivalent), and leave the rest of `AGENTS.md` as it is.
5. Reply with what was added, what was skipped because it already existed, and the next steps in this order:
   1. `product` → `PRODUCT.md`
   2. `user-journey` → `USER-JOURNEY.md`
   3. `architecture` → `ARCHITECTURE.md`, then the Commands table in `AGENTS.md`
   4. `design` → `DESIGN.md`
   5. `spec` for each feature, then build

## Guidelines

- Only copy the files listed above. Never copy the toolkit's own README, LICENSE, `skills/`, `.claude-plugin/` or `templates/` into the project.
- Don't commit. Leave the new files for the user to review.
