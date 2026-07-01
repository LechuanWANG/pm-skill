# Conversation Source: 2026-07-01 Skill Rule Updates

## Source Metadata

- Source id: `conversation-2026-07-01-raw-and-github-search`
- Provider: user instruction in the current conversation
- Observed: 2026-07-01
- Confidence: high for user intent; medium for future behavioral impact until exercised on real tasks.
- Scope: Durable user instructions about LLM Wiki raw-source granularity and brainstorming-stage GitHub prototype search behavior.

## User Confirmations

- Raw source granularity should be broad: the whole skill, the whole project, and the conversation can be treated as raw sources when the scope is clear.
- Raw storage does not need to be squeezed entirely into `raw/sources.md`; new files under `raw/` are acceptable for conversation ingests or other larger sources.
- The skill should make proactive GitHub search more likely during brainstorming for similar product directions and implementation references.

## Applied Rule Changes

- `pm-skill/SKILL.md` now says raw sources can be single files, whole skills, whole project snapshots, repository history slices, or high-value conversation portions.
- `pm-skill/references/llm-wiki-protocol.md` now separates `raw/sources.md` as a registry from additional `raw/` files used for longer source records.
- `pm-skill/references/brainstorming.md` now treats GitHub prototype/open-source search as a default consideration for new AI products, major features, Agent/RAG/workflow, UI patterns, and uncertain technical directions.
- `pm-skill/references/open-source-ideas.md` now defines when to search GitHub, how to query, how to filter, and how to record durable findings.

## Storage Boundary

This raw file records durable user instructions and applied changes only. It intentionally does not store the full chat transcript, transient implementation chatter, command noise, private data, or unrelated reasoning.
