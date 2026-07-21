---
description: Pre-merge check — launches the review of the current changes in parallel (qa + code-reviewer + security + the language specialist) and consolidates a single verdict.
argument-hint: "[optional base branch, e.g. main]"
---

Run a **preflight check** on the current changes before committing/merging$ARGUMENTS.

## Steps
1. **Scope the real diff**: run `git diff` and `git status` (or `git diff <base>` if the
   user gave a base). If there are no changes, say so and stop.
2. **Detect the stack** of what changed (TS/JS, Python, SQL/migrations, UI, infra) to
   decide which specialists to add.
3. **Launch the reviewers IN PARALLEL** as subagents (multiple tool calls in one message),
   each focused ONLY on its lens and on the same diff:
   - `code-reviewer` → correctness, readability, consistency, general security. (always)
   - `security-reviewer` → secrets, injection, authz, sensitive data, OWASP. (always)
   - `qa-engineer` → missing edge cases, missing tests, how to break it. (always)
   - `typescript-reviewer` → if there's TS/JS.
   - `python-reviewer` → if there's Python.
   - `database-reviewer` → if there's SQL/migrations/schema.
   - `silent-failure-hunter` → if there's non-trivial error handling / async / network / IO.
4. **Consolidate** all findings into ONE report, deduplicating overlaps:
   - Order by severity: 🔴 blocking · 🟡 recommended · 🟢 nice-to-have.
   - Each item with `file:line`, issue, impact, and proposed fix.
   - **Final verdict**: ✅ ready to merge · ⚠️ merge with conditions · ⛔ do not merge.
5. If there are 🔴 blockers, offer to hand the fixes to `fullstack-dev`.

## Rules
- Don't approve while anything 🔴 is unresolved.
- Don't invent problems to justify the review; if it's clean, say so clearly.
- Verify claims by reading the code, don't assume.
