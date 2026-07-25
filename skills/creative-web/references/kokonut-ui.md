# Kokonut UI

A shadcn-style registry of 100+ polished, animated React components — marketing blocks,
cards, buttons, inputs, backgrounds. Own-the-code: the CLI writes the component source
*into* your repo, so you edit it freely.

- **Site / docs:** https://kokonutui.com · https://kokonutui.com/docs
- **License/cost:** Free open-source tier (100+ components, on GitHub) + paid **Kokonut UI Pro**
  (70+ extra components/templates). Check per-component whether it's free or Pro.

## Stack it assumes
React + **Next.js** + **Tailwind CSS** + **shadcn/ui** + **Motion** (motion.dev) as the
animation runtime. You need a shadcn + Tailwind project already set up.

## How to use
```bash
# in an existing shadcn + Tailwind project
npx shadcn@latest add @kokonutui/<component-name>
```
The command drops the component's source into your `components/` (own-the-code). Import and
use it like any local component; tweak freely.

## When to use
- You want polished, pre-built *animated* blocks fast instead of authoring motion from scratch.
- General marketing/product UI (heroes, feature sections, cards, CTAs, backgrounds).
- You're already on the shadcn + Tailwind + Next stack.

## When NOT to use
- Not on React/Next + shadcn + Tailwind → it won't fit (use anime.js/Motion directly).
- Data-viz / charts → use **Bklit UI** instead (they complement, not overlap).

## Gotchas
- Requires shadcn CLI + Tailwind configured first.
- Pulls in Motion as the animation runtime — React/Next only, not vanilla.
- Confirm free vs Pro before depending on a specific component.
