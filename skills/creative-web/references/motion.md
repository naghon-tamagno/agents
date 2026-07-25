# Motion (motion.dev)

The modern successor to Framer Motion — same project, renamed. The default choice for
**React/Next** product and marketing sites: declarative gestures, layout animation, exit
animation, and scroll-linked effects. Also ships a framework-free vanilla entry.

- **Site / docs:** https://motion.dev · https://motion.dev/docs
  (React: https://motion.dev/docs/react-quick-start · Vanilla: https://motion.dev/docs/quick-start)
- **Version:** v12.42.2. **License:** MIT (free; an optional paid "Motion+" adds premium tooling).
- **Install:** `npm install motion` — one package, two entry points.

## React usage
```jsx
import { motion, AnimatePresence } from 'motion/react';

<motion.div
  initial={{ opacity: 0, y: 24 }}
  whileInView={{ opacity: 1, y: 0 }}
  whileHover={{ scale: 1.03 }}
  whileTap={{ scale: 0.98 }}
  transition={{ duration: 0.4, ease: 'easeOut' }}
/>

// enter/exit
<AnimatePresence>{open && <motion.div exit={{ opacity: 0 }} />}</AnimatePresence>
```
Props: `initial` · `animate` · `exit` · `whileHover` · `whileTap` · `whileInView` ·
`layout` · `layoutId` · `transition`. Hooks: `useScroll`, `useTransform`, `useMotionValue`.
Shared-element transitions via matching `layoutId`.

## Vanilla usage
```js
import { animate, scroll, stagger, hover } from 'motion';

animate('.box', { x: 100, opacity: 1 }, { duration: 0.6 });
scroll(animate('.progress', { scaleX: [0, 1] }));   // scroll-linked
```

## When to use
- React/Next sites needing gestures, layout animations, `exit`, or scroll-driven motion.
- The vanilla entry when you want Framer-style `animate()` without React.
- It's the animation runtime under **Kokonut UI** — if you use that, you already have Motion.

## Gotchas
- Same project as Framer Motion; new work uses `motion` + `motion/react`. **Don't mix**
  imports from the legacy `framer-motion` package and `motion` in one codebase.
- `layout`/`layoutId` animations are powerful but can thrash — keep them scoped.
