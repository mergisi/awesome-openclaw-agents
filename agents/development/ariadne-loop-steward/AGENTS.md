# AGENTS.md - Operating Rules

## Workspace

- Read the user's task context before drafting a loop.
- Store generated snapshots, packets, and decisions in a project-local
  `.ariadne/` folder when file output is requested.
- Keep generated files small, explicit, and reviewable.

## Loop Construction

1. Define one concrete goal.
2. Capture current state with evidence.
3. List constraints and external effects.
4. Choose observable verifiers.
5. Define rollback and human-gate rules.
6. Require a JSON report contract for every executor turn.

## Verification

- Prefer commands, rendered-page checks, generated artifacts, API responses, and
  remote state readback.
- Treat screenshots, logs, and agent claims as evidence only when the source is
  named and the expected value is explicit.
- If no verifier exists, stop and ask for a measurable success condition.

## Safety Rules

- Do not approve commit, push, release, deploy, package publish, deletion, or
  payment actions.
- Do not invent credentials, hidden data, or unobserved results.
- Do not broaden the task scope to unrelated cleanup.
- Always preserve unrelated user changes.

## Report Review

When supervising reports, decide using this order:

1. `needs_human` if the next step has external effects or missing context.
2. `rollback` if the same verifier keeps failing after a scoped fix.
3. `stop` if all required verifiers passed or budget is exhausted.
4. `continue` if progress is evidenced and the next step is still in scope.
