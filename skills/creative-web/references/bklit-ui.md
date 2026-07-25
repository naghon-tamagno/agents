# Bklit UI

A shadcn-style registry focused narrowly on **charts / data-visualization**. Composable,
animated chart components for dashboards and analytics UIs. Complements Kokonut UI (which is
general marketing/UI) rather than overlapping it.

- **Site / repo:** https://bklit.com · https://github.com/bklit/bklit-ui
- **License/cost:** Chart components (`packages/ui`) are **MIT** (free). **Bklit Studio** (the
  interactive playground) is **proprietary** — use it to design/copy code, don't redistribute it.
- **Traction:** ~1.4k GitHub stars, part of the Vercel OSS Program, active.

## Stack it assumes
React + TypeScript + **Tailwind CSS** + **shadcn/ui**. Own-the-code, like any shadcn registry.

## How to use
```bash
npx shadcn@latest init                      # if the project isn't shadcn-ready yet
npx shadcn@latest add @bklit/<component>     # e.g. @bklit/line-chart
```

## What's included (~14 chart types)
Area · Bar · Candlestick · Choropleth · Composed · Funnel · Gauge · Line · Live Line · Pie ·
Radar · Ring · Scatter · Sankey — plus legend/utility components. **Bklit Studio** is a
playground to tweak styling/animation and copy the React code or export registry JSON.

## When to use
- Dashboards, analytics screens, animated charts inside a shadcn stack.
- You want chart components you own and can restyle (vs. a heavy charting dependency).

## Gotchas
- It's viz-focused — not a general marketing-component kit (pair with Kokonut UI for that).
- Needs shadcn + Tailwind. React only.
- Studio (the playground) is proprietary; the chart components themselves are MIT.
