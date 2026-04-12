---
title: "Kaupang"
tagline: A sovereign marketplace for agent skills and plugins. Versioned, searchable, and running on our own metal.
year: 2026
status: ongoing
type: tool
sort_key: 2026.6
---

<figure class="project-hero">
  <img src="{{ "/assets/kaupang/kaupang-hero.svg" | relative_url }}" alt="Kaupang — GL·06 sovereign agent marketplace, slate blue seal on dark">
</figure>

Someone on the team rebuilt a skill that already existed on a colleague's laptop. Same problem, slightly different name, zero awareness either person had done the work. That was the third time it had happened in a month, and the last one before we decided the gap was worth naming.

Kaupang — Old Norse for the Viking-age trading posts that hosted merchants from across the North Sea — is an internal marketplace for agent capability. Skills and plugins that used to pass through chat messages and local folders now live in one registry: versioned, labelled against specific agent runtimes, and searchable the way anyone would expect them to be.

### What it does

Kaupang indexes two kinds of asset: SKILL.md-based skills and installable plugins — the shape Claude Code, Codex, and Copilot are all converging on. Publishers upload a `.tar.gz` or `.zip`; Kaupang auto-detects the type, validates the manifest, stores the bundle, and records a version history. Anyone on the network can then search by keyword, filter by runtime, read the compatibility matrix, and retrieve the exact version they need.

The same four operations — search, evaluate, retrieve, publish — are exposed three ways: a REST API, an MCP server that Claude Desktop, Cowork, and Codex connect to over SSH stdio, and a web UI for the hands-on cases. There is no primary interface. Each surface hits the same service layer and sees the same data.

### The stack

A TypeScript monorepo: Hono on Node 20 for the API, MCP, and static SPA serving; PostgreSQL 16 with Drizzle ORM and its own full-text search; React 19 + TanStack Router + Tailwind v4 for the web. The `@modelcontextprotocol/sdk` gives us the stdio and SSE transports without ceremony. Bundles are stored on a bind-mounted filesystem; swapping for S3 is one interface change.

The whole thing ships as a single multi-stage Docker image that runs as an unprivileged user and auto-migrates on startup. Everything that accepts user input — REST body, multipart upload, MCP tool argument — is validated by a shared Zod schema before it reaches the service layer. Publish rejects path traversal, zip-slip entries, and symlinks before the first byte hits disk; archives from macOS Finder with their `__MACOSX/` metadata siblings are handled cleanly, which broke us twice before we learned.

### Vendor-aware, not vendor-locked

OpenAI treats skills as the authoring format and plugins as the distribution unit. Anthropic uses SKILL.md as modular capability and bundles them into installable plugins with a different packaging model. Microsoft is converging on adjacent but incompatible shapes. Any marketplace built around one vendor's packaging is stale the day it ships.

Kaupang stores the original manifest — the unmodified `plugin.json`, the raw SKILL.md frontmatter — and attaches a normalized metadata layer on top. The catalog describes assets in shared terms (type, surface, compatibility, lineage) while every retrieve returns the exact bytes the publisher uploaded. Adding a new vendor is a new enum value and a new validator, not a schema migration.

### Trust is a signal, not a claim

Every published version carries a compatibility matrix against seven known agent surfaces. Each row has a confidence level: declared (the author says it works), self-tested (they ran it), peer-verified (someone else ran it), automated-validated (CI confirmed it), incompatible (known broken), unknown (no data). Readers get to decide what confidence they need.

The trust hierarchy is encoded in the data model, not in a README. Downloads, ratings, and version activity all feed discovery. An asset with a year-old declared row sorts below one with a peer-verified entry from last week. That is the only kind of trust signal we have ever found useful: the kind a machine can actually read.

---

Built because we wanted it to exist. And because the third duplicate skill was the one that tipped the argument.
