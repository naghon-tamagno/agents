# Team and shared knowledge

These instructions apply in ALL projects (loaded at the user level). Anything
project-specific lives in that project's own `CLAUDE.md` and takes priority.

## You have a team of specialists
You can delegate to subagents depending on the task:
`tech-lead` (orchestrates), `architect`, `fullstack-dev`, `ai-engineer`, `ml-engineer`,
`qa-engineer`, `ux-designer`, `ui-designer`, `devops-engineer`, `code-reviewer`, plus the
on-demand specialists (`planner`, `security-reviewer`, `performance-optimizer`,
`database-reviewer`, `a11y-architect`, `seo-specialist`, `silent-failure-hunter`,
`refactor-cleaner`, `code-simplifier`, `tdd-guide`, `typescript-reviewer`, `python-reviewer`).

For large or ambiguous tasks, start by delegating to `tech-lead` so it plans and splits the
work. After writing code, go through `qa-engineer` and `code-reviewer` before calling
anything done (or just run `/preflight`).

## Shared knowledge across projects
Before deciding or fighting a problem, keep the team's knowledge in mind:

@/Users/santiagotamagno/projects/claude-code/team/knowledge/playbook.md
@/Users/santiagotamagno/projects/claude-code/team/knowledge/lessons.md
@/Users/santiagotamagno/projects/claude-code/team/knowledge/stack.md

## How learnings are shared
- **Reusable** learning across projects → goes to `team/knowledge/` (use `/retro`).
- **Project-specific** learning → goes to THAT project's `CLAUDE.md`.
- Claude Code's auto-memory is per-repo (independent per project). The bridge between
  projects is this shared knowledge.

## Guiding principle
One team, with one method and one shared memory — but each project is sovereign over its own
conventions. Never mix one project's configuration into another.

Respond in clear, direct Rioplatense Spanish.
