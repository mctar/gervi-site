---
layout: page
<<<<<<< HEAD
title: AX (AI Experience)
=======
title: AX
>>>>>>> 0410ca1 (Initial commit)
permalink: /ax/
description: AX Manifesto and stories from the probabilistic age.
---

Gervi Labs treats AX (AI Experience) as a full discipline. It’s how we design with intelligent, adaptive systems so that people and synthetic collaborators can share control.

## AX Manifesto: Ten Principles for Designing in the Probabilistic Age

Every discipline that touches digital products is shifting. The question isn’t if AI will change how we work, it’s how quickly we learn to work differently. Teams that adapt will ship products that feel conversational rather than mechanical, adaptive rather than brittle, and smarter with every interaction. Teams that cling to deterministic thinking will keep building yesterday’s products with yesterday’s methods.

This isn’t “add AI and stir.” It changes how individuals work, how teams collaborate, how leaders enable risk and learning, what we build, and how customers experience it. All layers must evolve together. At the product layer, we need new principles. That’s AX: designing with intelligent, adaptive systems.

### The ten principles

1. **Model-first empathy**  
   Start with what today’s models can and cannot do. Design from reality, not wishful thinking.
2. **Design for probability, not certainty**  
   Non-determinism is the norm. Embrace ranges, confidence, guardrails, and graceful fallback; don’t assume perfect paths.
3. **Experiment and experience while you design**  
   Prototype with live or stubbed models in the loop. If it isn’t testable in near real time, it isn’t ready to spec.
4. **Modality steers model behavior**  
   The interface is the instruction; let people switch between text, voice, vision, and gesture without losing context.
5. **Prompt craft is product craft**  
   System prompts are core. Version and A/B test them, and track outcomes.
6. **Trust and ethics are experience features**  
   Explainability, consent, privacy, safety, and red-teaming are part of the UI and the narrative, not checkboxes.
7. **Speed and cost are design decisions**  
   Latency changes perception. Token and compute budgets shape flows. Expose trade-offs and design for them.
8. **Build continuous learning loops**  
   Instrument uncertainty, capture feedback (with consent), and ship updates as frequently as content changes.
9. **Practice cross-disciplinary fluency**  
   Design × data × ML × infra work as one system. Share vocabularies, dashboards, and responsibility.
10. **Be unrelentingly curious**  
    Model behavior shifts weekly. Stay close to the frontier, and let your process evolve with it.

This is the beginning. Teams mastering these principles now are building the next generation of products, less like software and more like collaboration. Soon we will stop calling this AX; it will just be how products get made.

## AX stories

These field notes show AX in practice, from accelerated discovery sprints to high-stakes operational agents. Each entry links back to the manifesto while sharing concrete deliverables, metrics, and exercises.

{% if site.ax %}
  <ul class="project-list">
    {% assign ax_entries = site.ax | sort: "order" %}
    {% for entry in ax_entries %}
      <li class="project-list-item">
        <a class="project-title" href="{{ entry.url | relative_url }}">{{ entry.title }}</a>
        {% if entry.summary %}
          <p class="project-tagline">{{ entry.summary }}</p>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
{% else %}
  <p>AX stories coming soon.</p>
{% endif %}
