---
description: Implement a create-plan.md plan
agent: build
model: opencode-go/deepseek-v4-flash
subtask: true
---

Implement the plan in $1.

First, read the full plan before editing. Treat it as the source of truth.

Rules:

- Follow the plan's Scope Firewall exactly.
- Do not change files outside the allowed implementation/test paths unless the user explicitly approves the scope change.
- If the plan appears incomplete, contradictory, ambiguous, or requires forbidden scope, stop and ask the user one concise clarification question before continuing.
- If you are unsure about the intended behavior, test expectations, repository conventions, or whether a change is in scope, ask the user before guessing.
- Implement phase by phase, preserving each phase's do-not-proceed gate.
- Add or update tests as required by the plan, preferably before or alongside the implementation.
- Do not introduce forbidden patterns listed in the plan.
- Do not perform opportunistic refactors, formatting churn, or adjacent fixes.
- Preserve unrelated pre-existing worktree changes.

Before editing:

- Run `git status --short`.
- Identify pre-existing dirty files.
- Read the plan sections: Summary, Pipeline Map, Contract Matrix, Scope Firewall, Test And Verification Inventory, Implementation Phases, Forbidden Patterns, Final Verification.

During implementation:

- For each phase, make the smallest correct change.
- Run the phase's required tests/checks when feasible.
- Audit changed files against the phase and global scope firewall before continuing.
- Prefer visible failures/errors over silent failures, and prefer failing fast over failing late.

After implementation:

- Run the plan's Final Verification commands/checks when feasible.
- Run a final `git status --short`.
- Report an implementation receipt containing:
  - Pre-flight `git status --short` and pre-existing dirty files
  - Files changed for this plan, distinct from pre-existing changes
  - Commands/tests run and which contract rows they cover
  - Contract rows not verified and why
  - Tests expected to fail before the fix and pass after
  - Manual review checks and forbidden-path audit summaries
  - Confirmation every changed file is allowed by the scope firewall
  - Adjacent fixes intentionally deferred as out of scope
