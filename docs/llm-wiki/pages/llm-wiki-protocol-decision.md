---
type: decision
status: active
created: 2026-06-30
updated: 2026-07-01
sources:
  - ../raw/sources.md#llm-wiki-protocol
  - ../raw/sources.md#llm-wiki-improvement-plan
  - ../raw/sources.md#skill-main
  - ../raw/sources.md#conversation-2026-07-01-raw-and-github-search
  - ../raw/sources.md#workspace-edit-2026-07-01-raw-github-trigger
confidence: high
tags:
  - llm-wiki
  - knowledge-management
  - ingest
---

# LLM Wiki Protocol Decision

## Summary

The current decision is that `llm-wiki` is a general, LLM-maintained project knowledge layer. Its ingest boundary is long-term value, not topic category. `pm-skill` keeps the reusable maintenance protocol; each project keeps its own concrete knowledge in `docs/llm-wiki/`.

## Key Points

- Canonical project-local path: `docs/llm-wiki/`.
- Minimum structure is `index.md` and `log.md`; create `schema.md`, `raw/`, and `pages/` when the project has enough durable material.
- Raw sources are facts or evidence: files, URLs, PDFs, screenshots, notes, user-provided text, code analysis, or local inspections.
- Raw source granularity is intentionally flexible. A source can be a single file, directory, whole skill, whole project snapshot, repository history slice, external search result set, or high-value part of the current conversation, as long as scope, time boundary, provenance, access method, confidence, and summary are explicit.
- `raw/sources.md` is the source registry, not the only raw storage location. Longer source records can live in separate `raw/` files such as `raw/conversations/`, `raw/external/`, or `raw/project-snapshots/`, then be referenced by registry entries and wiki pages.
- Wiki pages are synthesized knowledge: concepts, entities, decisions, source summaries, comparisons, workflows, retrospectives, evaluations, analyses, and open questions.
- Ingest should update existing pages when possible rather than create isolated summaries by default.
- Source acquisition is bounded by user intent, permissions, privacy, copyright, and project scope.
- Write directly when the user asks to establish or maintain the wiki, when the work creates clear long-term value, or when new information corrects outdated wiki content.
- Ask first before bulk ingesting external or sensitive materials, saving local snapshots of external content, reorganizing the schema, or permanently storing chat-derived personal preferences. Conversation-derived raw sources should preserve user confirmations and decisions, not full chat noise.
- Do not write secrets, tokens, passwords, unredacted private data, unsupported high-confidence claims, or one-off command noise.
- New material that challenges old conclusions should use `disputed`, `superseded`, or an explicit contradiction block instead of silent overwrite.

## Evidence

- `docs/llm-wiki-improvement-plan.md` records the rationale for broadening the wiki from AI reflection notes to a general Markdown knowledge layer.
- `pm-skill/references/llm-wiki-protocol.md` is the current maintenance protocol and includes directory, ingest, query, lint, write-back, page template, and conflict guidance.
- `pm-skill/SKILL.md` routes project-local LLM Wiki work to the protocol and states that durable project knowledge belongs in `docs/llm-wiki/`.
- The 2026-07-01 user instruction explicitly confirmed whole skill, whole project, and conversation as acceptable raw source units, prompting the protocol update.
- `raw/conversations/2026-07-01-skill-rule-updates.md` demonstrates the updated storage pattern: conversation-derived source details live in a dedicated raw file while `raw/sources.md` remains the registry.

## Links

- [Project Overview](project-overview.md)
- [PM Skill Operating Model](pm-skill-operating-model.md)
- [Open Questions](open-questions.md)

## Open Questions

- If future work relies directly on the external Karpathy gist cited by the improvement plan, should the project keep a stable snapshot or a more explicit source-summary page for that external document?
- Should codebase-memory ADR support be used for repository-level decisions, or is this wiki decision page sufficient for the current project size?

## Change Notes

- 2026-07-01: Updated raw source granularity decision to allow broad source units, including whole skill, whole project snapshot, repository history slice, external search result set, and high-value conversation scope under explicit provenance and privacy boundaries. Clarified that `raw/sources.md` is a registry and additional `raw/` files can store longer source records.
- 2026-06-30: Created from the current protocol and improvement plan.
