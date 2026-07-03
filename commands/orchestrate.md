---
description: Orchestrate implementation of a .md plan file passed as argument
agent: code-orchestrator
model: openai/gpt-5.5
---

I want to implement the plan that is outlined in $1

Please use standard "implement/review/remediation plan" cycles, delegating work to the most appropriate sub-agent.

The plan is already described in $1 so you should be able to start by delegating this to the appropriate sub-agent(s) to implement the plan. You should not need to re-plan.

If the plan contains multiple phases, work through these as suggested in the plan

All sub-agents should be careful not to try to touch anything outside the current working directory

The review process should be conducted with reference to $1

Your job is to orchestrate this process - not to do any work yourself.

Do no overcomplicate the process. We have a clear plan, and should implement it an then review with respect to the original plan. We do not need to re-plan or overthink the process. The goal is to implement the plan as described, review it, and make any necessary remediations based on the review.