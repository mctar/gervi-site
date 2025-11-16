---
title: "Beyond the Screen, Part 1: From Interface to Behavior"
summary: Moving from screens to agent behavior, and the design patterns that keep humans in control.
order: 2
---

Earlier I shared the AX Manifesto, ten principles for designing with intelligent, adaptive systems. Principles only matter if they survive contact with reality. My recent work has focused on turning those ideas into practice: prototyping, testing agent behaviors, and building team learning tools.

I began by applying AX principles to real-time conversational LLMs. The next challenge came with agentic flows, systems that not only talk but act. My work now covers both, shaping a live, high-stakes operational agent. The core insight is simple: we are no longer designing screens. We are shaping behavior.

### When the medium is conversation

When the product acts through language, traditional design artifacts are no longer enough. We move from the deterministic world of pixels to a probabilistic one of intent and consequence.

- The UI is how it acts, not how it looks. I design how the agent reasons, expresses uncertainty, asks for consent, and recovers from error, turn by turn.
- The unit of work is a tool call. Each task, such as diagnosing a fault, retrieving a report, or changing a system state, must be wrapped in clear language, explicit confirmation, and a lasting audit trail.
- Probability is the natural state. Perfect flows do not exist. I design for confidence thresholds, graceful fallbacks when unsure, and safe rollbacks for critical actions.

### What my work looks like

- Map the system and tag risk levels for every tool, from read to write and reversible to permanent.
- Create the agent’s operational language that explains logic, requests consent, refuses unsafe actions, and logs outcomes.
- Design conversation flows using the pattern Diagnose → Propose → Verify → Act → Confirm, with recovery loops for ambiguity.
- Build trust and control with consent gates, responsible defaults, and transparent who-what-why logging.
- Establish evaluation loops with rubrics, error taxonomies, and transcript reviews that guide improvement.

This shift requires more than new skills. It calls for new deliverables that guide teams in building safe and reliable agents. In Part 2 I share the practical artifacts and metrics that turn this discipline into something ready to ship.
