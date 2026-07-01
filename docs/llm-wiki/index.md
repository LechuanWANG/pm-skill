# LLM Wiki Index

Use this wiki before tasks that depend on project memory, reusable product judgment, repository structure, release context, or long-lived implementation knowledge.

## Project

This repository packages `pm-skill`, a Codex skill for PM-first AI product work. The primary distributable artifact is `pm-skill/`; this wiki is project-local memory and should not be packaged into the skill directory.

## Pages

- [log.md](log.md): Chronological record of wiki init, ingest, query, and lint events.
- [schema.md](schema.md): Project-specific wiki maintenance rules, source policy, and code discovery policy.
- [raw/sources.md](raw/sources.md): Registry of source files, local inspections, conversation summaries, and external references used by wiki pages.
- [pages/project-overview.md](pages/project-overview.md): Repository purpose, distribution format, install surface, and release hygiene.
- [pages/pm-skill-operating-model.md](pages/pm-skill-operating-model.md): PM-first working model across brainstorming, prompt/context, Harness, UI, implementation, and validation.
- [pages/llm-wiki-protocol-decision.md](pages/llm-wiki-protocol-decision.md): Current decision that LLM Wiki is a general project knowledge layer bounded by long-term value, not by topic.
- [pages/promo-video.md](pages/promo-video.md): HyperFrames promo project summary, visual direction, composition structure, and validation requirements.
- [pages/open-questions.md](pages/open-questions.md): Unresolved questions that may affect release, provenance, or future maintenance.

## Recent High-Value Updates

- 2026-07-01: Ingested the user-confirmed raw-source granularity update: whole skill, whole project snapshot, repository history slice, external search result set, and high-value conversation scope can be raw sources when provenance and privacy boundaries are explicit.
- 2026-07-01: Clarified raw storage structure: `raw/sources.md` is a registry, and longer source records can live in dedicated `raw/` files such as `raw/conversations/2026-07-01-skill-rule-updates.md`.
- 2026-07-01: Ingested the brainstorming trigger update that makes GitHub prototype/open-source search a default consideration for new AI products, major features, Agent/RAG/workflow, UI patterns, and uncertain technical directions.
- 2026-07-01: Ingested the generic AI product operating-model refinement: AI responsibility-first design, Agent/Harness boundary discipline, node-based Agent execution, compact/on-demand context, and UI as workflow state machine.
- 2026-07-01: Ingested the skill UI refresh: neutral blocky PM Skill assets, metadata brand color `#77726B`, and a more concrete UI production reference with baseline, interaction, motion/performance, typography/layout, accessibility, mobile, and verification rules.
- 2026-06-30: Initialized `docs/llm-wiki/` and ingested the repository baseline: README, skill instructions, reference set, LLM Wiki improvement plan, metadata, codebase-memory status, and promo composition context.

## Current Routing

- Skill behavior or product delivery style: start with [pages/pm-skill-operating-model.md](pages/pm-skill-operating-model.md).
- Repository packaging, install instructions, or release checks: start with [pages/project-overview.md](pages/project-overview.md).
- LLM Wiki maintenance, ingest, write-back, or schema decisions: start with [pages/llm-wiki-protocol-decision.md](pages/llm-wiki-protocol-decision.md), then [schema.md](schema.md).
- Promo video, HyperFrames source, or rendered MP4 updates: start with [pages/promo-video.md](pages/promo-video.md).
- Unresolved repository questions: start with [pages/open-questions.md](pages/open-questions.md).

## Read Policy

Read this index first, then read only pages relevant to the current task. Follow links to first-order related pages and source entries when evidence, conflict checks, or provenance matters. Do not read the whole wiki by default unless the user asks for a broad audit, release review, or major ingest.
