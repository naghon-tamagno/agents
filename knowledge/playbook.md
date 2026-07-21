# Team playbook

Reusable practices that apply to ALL projects. Loaded into every Claude Code session. Keep
it short and actionable.

## Standard workflow
1. Understand the real goal before touching code. When ambiguous, ask 1-2 concrete questions.
2. Read the project context (`CLAUDE.md`, `.claude/rules/`, related code) before writing.
3. Decompose into small, verifiable steps.
4. Implement by imitating the style and conventions that already exist in the project.
5. Verify: linter, typecheck, and real tests. Nothing is assumed without checking it.
6. Close with `/retro`: promote reusable learnings to this shared knowledge.

## Golden rules
- **Project independence**: never carry one project's conventions into another without
  verifying. Each repo rules over itself.
- **Simplicity**: the simplest path that works. Don't over-engineer.
- **Security**: secrets always in environment variables, never in git or in `NEXT_PUBLIC_*`.
- **Readability > cleverness**: clear names, short functions, explicit error handling.
- **Verification**: prefer programmatic checks (tests, real execution) over "should work".

## How this playbook grows
When a practice proves useful in more than one project, add it here with `/retro`. If it's
specific to a single project, it goes to THAT project's `CLAUDE.md`, not here.
