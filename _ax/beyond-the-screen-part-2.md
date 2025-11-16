---
title: "Beyond the Screen, Part 2: The Practitioner’s Playbook"
summary: Deliverables and metrics for trustworthy AI agents that move beyond chatbot demos.
order: 3
---

In Part 1, I outlined the mindset shift required to design AI agents, moving from designing screens to shaping behavior. But what does this work actually produce? Here is the practical playbook, the core deliverables and new metrics we use to build agents you can trust.

### Deliverables

This work produces a set of core documents that serve as the blueprint for the agent's behavior. These aren't hypothetical artifacts; they guide the team:

- **Stance & Voice One-Pager:** Defines the agent's tone, scope, and boundaries, informing the final system prompt.
- **Capability Catalogue:** A detailed inventory of every tool, complete with risk tags (e.g., \[Read-Only, Low-Risk] vs. \[Write, High-Risk, Reversible]).
- **Playbook of Critical Messages:** A version-controlled set of pre-approved text for crucial interactions, embedded into the system prompt.
- **Conversation Maps:** Visual blueprints of the turn-by-turn dialogue for a key task.
- **Trust Contract:** Rules of engagement outlining the logic for confirmations or escalations.
- **Performance Scorecard:** Metrics and rubrics to grade the agent's responses, driving learning and improvement.

### An example in practice

```
User: “What’s the status of the Phoenix project’s deployment?”
Agent: “I’m seeing a critical error in the pre-flight check for the database migration. This is the same error we saw last week. Do you want me to apply the same rollback procedure?”
User: “Yes, do it.”
Agent: “Executing rollback… Done. The system is now stable. I’ve logged the incident and the action you authorized under ticket #8675.”
```

This exchange demonstrates the core principles: the agent observes, provides context, proposes a clear action, waits for explicit consent, confirms completion, and provides an audit trail.

### Metrics that matter

I’m no longer tracking engagement or clicks. I’m measuring what matters in a high-stakes environment:

- **Task Resolution Rate:** How often does the agent successfully help the user complete their goal?
- **Time to Mitigation:** How much faster is a problem solved with the agent versus the manual baseline?
- **Confirmed-Action Accuracy:** Does the agent do exactly what it was authorized to do?
- **Audit Completeness:** Is every action logged with a clear who, what, and why?

This is the work of AX. It’s a real discipline, not title inflation. The deliverables and metrics above are the difference between building a chatbot demo and shipping an AI agent you can actually trust. This is where the future of product development is heading.
