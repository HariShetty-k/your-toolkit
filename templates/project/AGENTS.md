# AGENTS.md

Instructions for AI coding agents working in this repository. Keep this file short: commands, conventions, and where to find context.

## Project Docs

Read these before making changes. They are the source of truth.

| File | Read it when |
|------|--------------|
| `PRODUCT.md` | Always: what we're building, for whom, and why |
| `ARCHITECTURE.md` | Always: stack, where code lives, decisions, and rules |
| `DESIGN.md` | Before any UI work: colors, type, spacing, components |
| `USER-JOURNEY.md` | Before building or changing a user-facing flow |
| `specs/` | Before working on a feature that has a spec |

If a change conflicts with one of these docs, stop and ask. Don't silently diverge. If the change is agreed, update the doc in the same change.

## Commands

<!-- Fill these in once the stack is chosen. -->

| Task | Command |
|------|---------|
| Install | |
| Dev server | |
| Test | |
| Lint | |
| Typecheck | |
| Build | |

## Workflow

1. For anything bigger than a small fix, write a spec first in `specs/` (see `specs/README.md`).
2. Make the smallest change that meets the spec's acceptance criteria.
3. Add or update tests for the change.
4. Run test, lint, and typecheck before saying the work is done.
5. Tick off the task in the spec's `tasks.md`.

## Conventions

<!-- Add project-specific rules here as they come up, e.g. "use server actions, not API routes". -->

- Follow the rules in `ARCHITECTURE.md`.
- Never commit secrets. Use environment variables and keep `.env` files out of git.
