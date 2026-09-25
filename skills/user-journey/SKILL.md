---
name: user-journey
description: Create or update USER-JOURNEY.md, mapping personas, journey stages, and key flows. Use when the user asks for a user journey, user flows, personas, onboarding flow, or wants to plan how people will move through the product.
---

# User Journey

Write `USER-JOURNEY.md` at the project root describing how users move through the product.

## Steps

1. Read `PRODUCT.md` at the project root if it exists. The persona and flows must match its target users and core features. If it doesn't exist, suggest running the `product` skill first, but continue if the user wants to.
2. Check whether `USER-JOURNEY.md` already exists. If it does, update it in place.
3. Look at the codebase for real flows (routes, screens, signup and onboarding code) so the journey matches what's built or planned.
4. Fill in the template at `../../user-journey.md` (relative to this skill's directory):
   - One persona per section. Add more personas only if `PRODUCT.md` names more than one user type.
   - Fill every cell of the journey stages table. Rename or drop stages that don't fit the product.
   - Write 2–4 key flows as numbered steps, each with a clear success state.
5. Save as `USER-JOURNEY.md` at the project root. List any open questions for the user at the end of your reply.

## Guidelines

- Write from the user's point of view ("I want to…"), not the system's.
- Pain points and drop-off risks are the most useful part. Be specific about them.
