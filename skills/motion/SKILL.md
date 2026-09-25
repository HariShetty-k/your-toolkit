---
name: motion
description: Add animation to React UI with Motion (formerly Framer Motion). Use when the user asks for animations, transitions, hover or tap effects, scroll-triggered reveals, page or modal enter/exit, layout animations, or wants the UI to feel more alive or polished.
---

# Motion

Animate React UI with [Motion](https://motion.dev), the library formerly called Framer Motion.

## Setup

1. Check `package.json` first:
   - `motion` installed: import from `"motion/react"`.
   - Only `framer-motion` installed: keep it and import from `"framer-motion"`. The API is the same. Don't add a second package.
   - Neither: install `motion` with the project's package manager.
2. In Next.js App Router, components that use `motion` need `"use client"` at the top.

## Match the design

If `DESIGN.md` exists at the project root, read it first. Follow any motion, easing, or duration rules it gives. If it has none, match its overall feel: calm and subtle for minimal or editorial designs, bolder for playful ones.

## Defaults

- Durations: 150–250ms for hover and tap, 200–400ms for enter and exit, up to 600ms for large page-level moves.
- Use springs for things users touch or drag, and ease-out curves for things appearing on screen.
- Animate `transform` (x, y, scale, rotate) and `opacity`. Avoid animating `width`, `height`, `top`, or `left`; use the `layout` prop for size and position changes instead.
- Distances should be small: 8–24px slides, 0.95–1.05 scales.
- Respect reduced motion. Wrap the app once:
  ```tsx
  import { MotionConfig } from "motion/react"

  <MotionConfig reducedMotion="user">{children}</MotionConfig>
  ```

## Common patterns

```tsx
import { motion, AnimatePresence } from "motion/react"

// Fade and rise in on mount
<motion.div
  initial={{ opacity: 0, y: 12 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.3, ease: "easeOut" }}
/>

// Reveal when scrolled into view (once)
<motion.section
  initial={{ opacity: 0, y: 24 }}
  whileInView={{ opacity: 1, y: 0 }}
  viewport={{ once: true, margin: "-80px" }}
/>

// Hover and tap feedback
<motion.button whileHover={{ scale: 1.03 }} whileTap={{ scale: 0.97 }} />

// Exit animations: the child needs a stable key
<AnimatePresence>
  {open && (
    <motion.div
      key="modal"
      initial={{ opacity: 0, scale: 0.96 }}
      animate={{ opacity: 1, scale: 1 }}
      exit={{ opacity: 0, scale: 0.96 }}
    />
  )}
</AnimatePresence>

// Staggered list
<motion.ul
  initial="hidden"
  animate="show"
  variants={{ show: { transition: { staggerChildren: 0.05 } } }}
>
  {items.map((item) => (
    <motion.li
      key={item.id}
      variants={{ hidden: { opacity: 0, y: 8 }, show: { opacity: 1, y: 0 } }}
    />
  ))}
</motion.ul>

// Smooth size/position changes, and shared elements across components
<motion.div layout />
<motion.div layoutId="active-tab-indicator" />
```

## Don'ts

- Don't animate everything. Motion should point attention at what changed.
- Don't block interaction while an animation runs.
- Don't loop animations forever unless it's a loading state.
