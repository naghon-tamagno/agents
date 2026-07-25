---
name: creative-web
description: Toolkit for building distinctive, animated, high-craft websites — the antidote to generic templated landing pages. Use when adding motion (scroll, entrance/stagger, gestures, page transitions, SVG), picking drop-in animated components, or deciding between anime.js, Motion (motion.dev), Kokonut UI, and Bklit UI. Covers install, core API, and when to reach for each. Pairs with the creative-frontend agent.
---

# Creative Web — toolkit for sites that don't look templated

The goal: stop shipping the same generic hero + three cards. This skill is the verified
toolkit for building sites that feel designed and alive, plus how to choose the right tool
for each job. **Read the relevant `references/*.md` before writing code — don't reconstruct
a library's API from memory.**

## Pick the right tool

| You want… | Reach for | Stack | Model |
|---|---|---|---|
| Imperative timelines, SVG draw/morph, scroll & draggable, fully vanilla | **anime.js** | Vanilla JS (any framework) | `references/anime-js.md` |
| Declarative React motion: gestures, layout, `exit`, scroll-linked | **Motion** (motion.dev) | React/Next (also has a vanilla entry) | `references/motion.md` |
| Drop-in animated marketing/UI blocks (own-the-code) | **Kokonut UI** | React + Next + Tailwind + shadcn + Motion | `references/kokonut-ui.md` |
| Animated charts / dashboards / dataviz | **Bklit UI** | React + Tailwind + shadcn | `references/bklit-ui.md` |
| A fast first-draft site or pure inspiration (AI, not a dependency) | **Manus** | External AI platform | `references/manus.md` |

Rules of thumb:
- **Motion is the animation engine under Kokonut UI** — they compose, they don't compete.
- Both **Kokonut UI and Bklit UI are shadcn registries**: they write source *into* your repo
  (own-the-code) and require the shadcn CLI + Tailwind. React/Next only.
- **anime.js** is the pick when you're not on React or want deep timeline/SVG control.
- **Manus is not a library** — it's an AI agent platform (inspiration / first draft), never a
  build-block dependency. Don't `npm install` it.

## 30-second installs (verified)
```bash
npm install animejs      # anime.js v4  → import { animate, createTimeline, stagger } from 'animejs'
npm install motion       # Motion v12   → import { motion } from 'motion/react'  (or 'motion' for vanilla)
npx shadcn@latest add @kokonutui/<name>   # Kokonut UI component (needs shadcn + Tailwind)
npx shadcn@latest init && npx shadcn@latest add @bklit/<component>   # Bklit UI charts
```

## Workflow
1. **Start from a point of view, not a template.** Choose one bold idea / reference / mood
   with `ui-designer` before markup. Distinctive comes from a deliberate decision, not a kit.
2. **Match the project stack** (`CLAUDE.md`, existing deps). Add the *smallest* set of tools
   that buys the effect — don't pull three animation libs for one tween CSS could do.
3. **Choose the tool** from the table, then read its reference for the real API.
4. **Animate with restraint and taste**: motion serves hierarchy and feedback, not decoration.
5. **Non-negotiables**: honor `prefers-reduced-motion`; animate `transform`/`opacity` (not
   layout) for 60fps; never block content on animation; keep the bundle honest.
6. **Verify in the browser**: no jank, graceful degradation, reasonable bundle.

## Accessibility & performance guardrails
- Wrap non-essential motion in `@media (prefers-reduced-motion: no-preference)` (CSS) or gate
  it with `matchMedia('(prefers-reduced-motion: reduce)')` / Motion's reduced-motion support.
- Prefer compositor-friendly properties; avoid animating `width`/`height`/`top`/`left`.
- Lazy-load heavy effects; a beautiful site that's slow is a failed site.
- Hand deep perf work to `performance-optimizer` and deep a11y to `a11y-architect`.
