---
name: design
description: Create DESIGN.md, the design system doc agents follow when building UI. Use when starting a project's UI, when the user wants the app to look like a known brand or product (e.g. "make it look like Linear/Stripe/Notion"), or asks for a design system, colors, typography, or visual style.
---

# Design

Put a `DESIGN.md` at the project root so all UI work stays visually consistent. Designs come from the [awesome-design-md](https://github.com/voltagent/awesome-design-md) collection (MIT License).

## Steps

1. Check whether `DESIGN.md` already exists at the project root. If it does, ask before replacing it.
2. Pick a design:
   - If the user named a brand or style, find it in the collection list in `../../design.md` (relative to this skill's directory).
   - Otherwise, read `PRODUCT.md` if it exists and suggest 2–3 designs from that list that fit the product and audience, with one line each on why. Let the user choose.
3. Get the slug from the design's link: `https://getdesign.md/<slug>/design-md`. For example, Linear's slug is `linear.app` and Claude's is `claude`.
4. Download the file:
   ```
   https://raw.githubusercontent.com/VoltAgent/awesome-design-md/main/design-md/<slug>/DESIGN.md
   ```
   If that fails, tell the user and point them to `https://getdesign.md/<slug>/design-md` to download it by hand.
5. Save it as `DESIGN.md` at the project root without editing its contents.
6. Reply with a short summary: the main colors, fonts, and overall feel.

## Custom designs

If the user wants their own design instead of a brand's, write `DESIGN.md` from scratch with the 9 sections listed in `../../design.md` under "What's Inside Each DESIGN.md". Give real hex values, font names, and sizes, not vague descriptions.

## Building UI

When building any UI in a project that has a `DESIGN.md`, read it first. It is the source of truth for colors, type scale, spacing, and component styles. Follow its Do's and Don'ts.

Use these tools when they fit the task, and always restyle what they produce to match `DESIGN.md`:

- **Ready-made components and sections** (heroes, navbars, pricing tables, cards, containers, forms): if the 21st.dev tools (`search`, `get_component`) are available, search there before writing a component from scratch. Swap its colors, fonts, radii, and shadows for the `DESIGN.md` values after installing it. If the tools aren't available, tell the user they can install the `21st` plugin from this marketplace, then build the component by hand.
- **Animation** (transitions, hover effects, scroll reveals, enter/exit): use the `motion` skill.
