# OpenCode agents & commands

These are the agents (i.e., specialised LLM-based agent personas) and commands (i.e., pre-defined, reusable prompts) that I use with [OpenCode](https://opencode.ai).

Normally I use the following workflow for any large or risky change:

1. Discuss the task with the built-in "plan" agent, or use the `/grill-me` command to determine a plan for more complex tasks where I want to be sure that the LLM understands the requirements.
2. Use the `/create-plan` command to generate a plan - this will generate a plan that satisfies various requirements
3. Clear context, and then use the `/orchestrate` command (e.g., `/orchestrate plan.md`) with the `code-orchestrator` agent to implement the plan. This will:
   1. Implement the plan
   2. Review the implementation against the plan
   3. If significant issues are found, the orchestrator will ask for a remediation plan to be written
   4. Implement the fixes
   5. Review again, and repeat until the implementation is correct and complete.

This cycle ensures that implementation and review are carried out by sub-agents with their own context, and uses the original plan as a fixed guide for what should and shouldn't be done.

Using this approach seems to minimise the risk of the agent doing things it shouldn't, or missing key requirements, but it's still important to manually check what it produces!