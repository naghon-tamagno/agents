# Lessons learned (cross-project)

Already-solved mistakes and patterns that worked, shared across all projects. Before
fighting something, check whether it's already here.

Format for each entry:
- **[date] Short title** — Context → What happened → What to do / avoid. (project where discovered)

---

## Deploy / Infra

- **[seed] Vercel: secrets and models** — Never hardcode secrets or put them in
  `NEXT_PUBLIC_*`. With Vercel AI Gateway, verify the real model catalog
  (`curl https://ai-gateway.vercel.sh/v1/models`) before pinning a model string; don't
  trust IDs from memory. (aiforma)

## AI / Agents

- **[seed] Voice agents (Retell)** — Watch latency, interruption handling, and silences
  (configurable silence cutoff), plus conversational fallbacks. Agent/LLM IDs are not
  changed by hand without syncing. (aiforma)

## Frontend / UI

- _(empty — filled via `/retro`)_

## Backend / Data

- _(empty — filled via `/retro`)_

---

## How to add lessons
Use `/retro` at the end of a task. Only what's useful in MORE than one project goes here.
Anything project-specific goes to its own `CLAUDE.md`.
