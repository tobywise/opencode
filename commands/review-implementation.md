---
description: Review an implementation against a create-plan.md plan
agent: reviewer
model: openai/gpt-5.5
subtask: true
---

Review the implementation against the plan in $1.

This is a review-only task. Do not edit files.

First, read the full plan and treat it as the source of truth.

If the plan, implementation state, expected behavior, or review scope is ambiguous, ask the user one concise clarification question before assuming.

Review requirements:

- Compare changed files against the Scope Firewall.
- Verify every Contract Matrix row has matching implementation and proof.
- Verify every required positive test, negative test, manual check, grep/review check, and verification command was performed or has a justified gap.
- Check that forbidden patterns were not introduced.
- Check that implementation phases respected their gates.
- Check that the implementation receipt is complete, accurate, and consistent with the actual worktree.
- Distinguish pre-existing dirty files from files changed for this plan.
- Do not reward partial implementation just because tests pass.
- If you are unsure whether something is a bug, a plan gap, an acceptable deviation, or pre-existing work, ask the user instead of guessing.
- Check for silent failures. We have a clear preference for visible failures and failing fast over failing late.

Use a code-review mindset.

Output format:

1. Findings
   - List bugs, missing contract coverage, scope violations, weak tests, unverifiable claims, or behavioral regressions.
   - Order by severity.
   - Include file/line references where possible.
   - State which plan contract, phase, or scope rule is violated.

2. Open Questions
   - Include only questions that block review confidence.

3. Verification Summary
   - Commands/checks observed or still required.
   - Contract rows verified.
   - Contract rows not verified.

4. Scope Audit
   - Files changed.
   - Whether each changed file is allowed by the Scope Firewall.
   - Any forbidden or suspicious changes.

If there are no findings, state that explicitly and mention residual risks or unverified checks.

Write your findings to markdown with a clear and concise filename, using code snippets and file references where helpful. Be concise but specific. Avoid vague statements. Every finding should be actionable.
