---
title: "Mímir"
tagline: A sovereign live intelligence system that listens to a room, builds a knowledge graph in real time, and extracts what nobody noticed while they were inside the conversation.
year: 2026
status: ongoing
type: tool
sort_key: 2026.5
---

<figure class="project-hero">
  <img src="{{ "/assets/mimir/mimir-hero.jpeg" | relative_url }}" alt="Mímir — live knowledge extraction system">
</figure>

We needed something that did not exist yet.

At a Copenhagen event for a hundred executives, we wanted the room to see itself thinking. Not slides about thinking. The actual thoughts of the room, surfacing in real time, connecting, contradicting, evolving as the conversation moved through the day.

We had 24 hours. The next afternoon, Mímir ran its first live event.

### What it does

Mímir listens to a room. It transcribes speech as it happens. It builds a knowledge graph that grows and decays and rearranges itself on a screen behind the speakers, in front of the audience, while everyone watches. When the session ends, it generates recaps that find the connections nobody noticed while they were inside the conversation.

Mímir does not do summaries. It extracts knowledge.

### The stack

The transcription pipeline is built from Nvidia Parakeet and Canary STT models in containers, with faster-whisper as a fallback. The reasoning runs on Gemma 4, two sizes for two jobs. The 27B variant handles live entity extraction and graph updates inside a ten-second budget. The 12B variant takes over after the session ends and does the deeper analysis: the contradictions, the open threads, the threads of meaning nobody pulled on while the room was still talking.

It runs entirely on our own metal.

### Zero trust as architecture

Zero trust is not a marketing line in this build. It is the architecture. Every internal call between audio capture, the STT containers, the graph engine and the model server is mutually authenticated. The whole system runs air-gapped when we want it to. We have run it that way. It works.

### Why sovereignty matters

The conversations that matter most are the ones you cannot send to a vendor API. Strategy sessions. Board meetings. Customer interviews. Workshops where people speak openly because they trust the room. For those conversations, sovereignty is the precondition.

Tested in Oslo. Runs live in Paris. Built because we wanted it to exist.

<figure style="max-width: 240px; margin: 3rem auto;">
  <img src="{{ "/assets/mimir/mimir-logo-clean.svg" | relative_url }}" alt="Mímir logo" style="width: 100%;">
</figure>
