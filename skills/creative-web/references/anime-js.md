# anime.js (v4)

Lightweight, framework-agnostic JS animation engine. The pick for imperative timelines,
SVG line-drawing/morphing, scroll and draggable interactions — especially when you're NOT
on React or want vanilla portability.

- **Site / docs:** https://animejs.com · https://animejs.com/documentation
- **Version:** v4.5.0 (npm latest; the homepage label lags). **License:** MIT (free).
- **Install:** `npm install animejs` — ESM, modular, ~24.5 KB full.

## v4 API — named exports (NOT v3-compatible)
v4 was a full rewrite. The old default `anime({...})` / `anime.timeline()` is gone. Import
only what you use:

```js
import { animate, createTimeline, stagger } from 'animejs';

// basic tween
animate('.box', { translateX: 320, rotate: 90, duration: 800 });

// staggered list entrance
animate('.card', { opacity: [0, 1], translateY: [24, 0], delay: stagger(80) });

// sequenced timeline
const tl = createTimeline();
tl.add('.hero-title', { opacity: [0, 1], translateY: [40, 0] })
  .add('.hero-cta',   { scale: [0.9, 1] }, '-=200');
```

## Key primitives
`animate()` · `createTimeline()` · `stagger()` · `createDraggable()` · `createScope()` ·
`createMotionPath()` · `createDrawable()` (SVG line drawing) · `morphTo()` · `createSpring()`.

## When to use
- Vanilla / non-React sites, or islands inside any framework.
- SVG storytelling (draw-on, morph), motion paths, custom draggable UI.
- Fine-grained, imperative timeline control.

## Gotchas
- **v3 → v4 is breaking**: `anime.timeline()` → `createTimeline()`, default call → `animate()`.
  Don't copy v3 snippets from old tutorials.
- Confirm exact property/easing names against the docs — the API surface changed in v4.
- For React product UIs with gestures/layout/exit, prefer Motion instead.
