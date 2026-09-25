---
name: product
description: Create or update PRODUCT.md, the doc that tells agents what the project is, who it's for, and why. Use when starting a new project, when the user describes a product idea, or when asked to write down product goals, users, features, or success metrics.
---

# Product

Write `PRODUCT.md` at the project root so every later task has shared product context.

## Steps

1. Check whether `PRODUCT.md` (or `product.md`) already exists at the project root. If it does, update it in place instead of starting over.
2. Gather what you can before asking:
   - What the user has said in this conversation.
   - The codebase: README, package manifests, routes, and existing docs.
3. Ask the user only for what you still can't infer: usually the problem, target users, and goals. Ask in one short batch, not one question at a time.
4. Fill in the template at `../../PRODUCT.md` (relative to this skill's directory). Keep every section heading. Write "TBD" for anything still unknown rather than inventing it.
5. Save the result as `PRODUCT.md` at the project root and summarize what's still TBD.

## Guidelines

- Be concrete: "Freelance designers who invoice 5–20 clients a month", not "small businesses".
- Non-goals matter. They stop scope creep in later tasks.
- Success metrics should be measurable.
