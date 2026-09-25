---
name: architecture
description: Create or update ARCHITECTURE.md, describing the stack, codemap, data model, key flows, architecture decisions, and rules. Use when starting a project, choosing a tech stack, planning how a feature fits into the system, after a structural change, or when the user asks how the codebase is organized.
---

# Architecture

Write `ARCHITECTURE.md` at the project root so every session knows how the system is built and which rules to follow.

## Steps

1. Read `PRODUCT.md`, `DESIGN.md`, and `USER-JOURNEY.md` at the project root if they exist. The architecture must support the product's core features and key flows.
2. Check whether `ARCHITECTURE.md` already exists. If it does, update it in place. Keep existing decision numbers (AD-1, AD-2, …) and add new ones at the end.
3. Work out the current architecture from the code, not guesses:
   - Package manifests and lockfiles for the stack and versions.
   - The folder structure for the codemap.
   - Schema, migration, or model files for the data model.
   - Routes, handlers, and config for key flows, environments, and deployment.
4. For a new project with no code yet, propose a stack that fits `PRODUCT.md`. Prefer boring, well-supported choices. Give the user 1–2 options with trade-offs and let them decide before writing it down.
5. Fill in the template at `../../architecture.md` (relative to this skill's directory). Keep every heading. Write "TBD" for anything unknown rather than inventing it, and delete sections that truly don't apply.
6. Diagrams must be valid Mermaid that reflects the real system, not the template's example.
7. Save as `ARCHITECTURE.md` at the project root. In your reply, list the decisions you recorded and any open questions.

## Guidelines

- Short beats complete. Describe things that rarely change; the code owns the details.
- Name important files, modules, and types, but don't link to exact line numbers.
- Rules must be specific enough to check in a code review ("only `server/` imports the database client"), not vague ("keep code clean").
- When a later change breaks a rule, either fix the change or update the rule with a new decision. Don't let the doc silently drift.
