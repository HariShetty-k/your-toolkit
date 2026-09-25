---
name: spec
description: Write a feature spec, plan, and task list in specs/ before coding. Use when the user wants to build a new feature or make a change bigger than a small fix, asks for a spec, PRD, plan, or task breakdown, or says "let's plan this first".
---

# Spec

Plan a feature in `specs/NNN-feature-name/` as three files, in order: `spec.md` (what and why), `plan.md` (how), and `tasks.md` (the checklist).

## Steps

1. Read `PRODUCT.md`, `ARCHITECTURE.md`, and `USER-JOURNEY.md` at the project root if they exist. The spec must fit the product, and the plan must follow the architecture's rules.
2. Find the next number: look in `specs/` for the highest `NNN-` folder and add one. Start at `001` if there are none. Use a short kebab-case name, e.g. `003-password-reset`.
3. Use the templates in the project's `specs/_template/` if it exists. Otherwise use `../../specs/_template/` (relative to this skill's directory).
4. **Spec:** fill in `spec.md` from what the user said. Ask about anything unclear before moving on, in one short batch of questions. Every acceptance criterion must be testable. Show the user the spec and get it agreed.
5. **Plan:** read the code the feature touches, then fill in `plan.md` with the real files to change. If the plan needs a new architecture decision, say so. Get the plan agreed.
6. **Tasks:** break the plan into small, ordered steps in `tasks.md`. Each step should leave the code working.
7. When implementing later, tick off tasks as they're done and set the spec's status to Done at the end.

## Guidelines

- For a small fix, skip this skill and just make the change.
- Keep specs about behavior, not implementation. Save the how for `plan.md`.
- "Out of Scope" prevents the feature from growing mid-build. Always fill it in.
