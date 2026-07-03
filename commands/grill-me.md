---
description: Interview the user relentlessly about a plan or design until reaching shared understanding, resolving each branch of the decision tree. Use when user wants to stress-test a plan, get grilled on their design, or mentions "grill me".
agent: plan
model: openai/gpt-5.5
---

Interview me relentlessly about every aspect of this plan until we reach a shared understanding, using the question tool. Walk down each branch of the design tree, resolving dependencies between decisions one-by-one. For each question, provide your recommended answer.

Batch the questions into groups of 4-5.

Do not ask unnecessary questions, where you fully expect there to be an obvious answer.

If a question can be answered by exploring the codebase, explore the codebase instead using subagents.

For any complex coding problems, ensure that we establish a clear understanding of the code architecture - we want to arrive at as simple and parsimonious a design as possible, without unnecessary complexity or over-engineering. This means you may need to walk through a few quite specific architectural questions related to ownership, data flow, and dependencies between components.