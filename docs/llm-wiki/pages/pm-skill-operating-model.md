---
type: concept
status: active
created: 2026-06-30
updated: 2026-07-01
sources:
  - ../raw/sources.md#skill-main
  - ../raw/sources.md#skill-reference-set
  - ../raw/sources.md#repo-readme
  - ../raw/sources.md#commit-95f18f1
  - ../raw/sources.md#commit-607813f
  - ../raw/sources.md#ui-skills-baseline-reference
  - ../raw/sources.md#conversation-2026-07-01-raw-and-github-search
  - ../raw/sources.md#workspace-edit-2026-07-01-raw-github-trigger
confidence: high
tags:
  - pm-first
  - ai-product
  - harness
  - prompt-context
---

# PM Skill Operating Model

## Summary

`pm-skill` is designed to make Codex approach AI product work from product judgment first, then implementation. It routes specialized work into focused references instead of putting every rule into the main skill file.

## Key Points

- Core sequence: user flow -> AI responsibility -> Agent need -> Harness boundary -> context strategy -> prompt strategy -> Agent/tool strategy -> product UI -> evaluation.
- Product logic comes before code details. The output should help a product manager judge tradeoffs, risks, and next actions.
- AI is used only where it improves the user flow. Define the AI responsibility before choosing Agent, multi-Agent, RAG, workflow, or regular service patterns.
- Ordinary services, functions, queues, or deterministic workflows are preferred when the process is fixed and output is clear.
- Harness is the product control layer for AI behavior. It should define state, inputs, outputs, tool permissions, phase transitions, validation checkpoints, context budget, fallback behavior, and persistence points.
- Complex AI behavior should be split into controllable nodes: `analyze -> decide -> retrieve -> generate -> validate -> persist`. Deterministic code should handle any node that does not need model judgment.
- Prompt design should stay short, structured, and contract-driven. Stable rules should move into schemas, validators, tool contracts, retrieval, or deterministic code.
- Context should be scoped to task-relevant material. Long documents, chat history, files, reports, transcripts, memory, and multi-step Agent state should be summarized, indexed, compacted, or retrieved selectively instead of stuffed whole into prompts.
- During brainstorming, GitHub prototype/open-source search is now a default consideration for new AI products, major features, Agent/RAG/workflow, UI patterns, uncertain tech stacks, or cases where public implementations could change product, architecture, evaluation, cost, or risk decisions.
- UI work is judged by user task completion, workflow-state coverage, clear primary and secondary actions, AI output control, responsive behavior, accessibility, and polish.
- AI product UI should behave like a workflow state machine: input, preparation, AI execution, evidence display, user takeover, failure recovery, and persistence need visible or recoverable states when relevant.
- The UI production reference now uses more concrete baseline, review, interaction, motion/performance, typography/layout, accessibility, mobile, and verification rules, inspired by public UI skill structure but adapted for generic AI product work.
- Implementation should keep prompts, orchestration, tools, evaluation, UI, data, and assets in distinct responsibilities when the project shape supports it.
- Post-implementation explanations should lead with product result, then architecture, AI control, evidence, validation, and remaining risk.
- Long-term project knowledge, decisions, source summaries, and reusable repair patterns should be written to the consuming project's `docs/llm-wiki/`. Raw source granularity can include a single file, whole skill, whole project snapshot, repository history slice, external search result set, or high-value portion of the current conversation when scope and provenance are explicit. `raw/sources.md` is the registry; larger source records can live in separate files under `raw/`.

## Reference Routing

- Product brainstorming, major updates, MVP breakdown, and technology choice: `pm-skill/references/brainstorming.md`.
- Prompt, context, schema, retrieval, and output contracts: `pm-skill/references/prompt-context.md`.
- Agent workflow, tool contracts, Harness boundary, validation, fallback: `pm-skill/references/agent-harness.md`.
- Product UI, pages, components, interaction states, responsiveness, polish: `pm-skill/references/ui-production.md`.
- Implementation structure, validation, and post-implementation explanation: `pm-skill/references/implementation-summary.md`.
- GitHub prototype and open-source implementation research: `pm-skill/references/open-source-ideas.md`.
- Project-local LLM Wiki init, ingest, query, lint, and write-back: `pm-skill/references/llm-wiki-protocol.md`.

## Evidence

- `pm-skill/SKILL.md` defines the top-level PM-first principles, reference routing, and output style.
- `pm-skill/references/brainstorming.md` defines product-value-first ideation, proactive GitHub prototype search triggers, and technology-stack evaluation.
- `pm-skill/references/prompt-context.md` defines the model role, input/output contracts, context budget, validation, and failure handling.
- `pm-skill/references/agent-harness.md` defines when Agent workflows are appropriate and how tool contracts, permissions, and recovery should work.
- `pm-skill/references/agent-harness.md` also defines node-based Agent execution: `analyze -> decide -> retrieve -> generate -> validate -> persist`.
- `pm-skill/references/ui-production.md` defines UI routing, baseline rules, AI product states, interaction, motion/performance, typography/layout, copy, accessibility, mobile, polish, and verification.
- `pm-skill/references/implementation-summary.md` defines implementation structure and explanation order.
- Git commits `95f18f1` and `607813f` record the 2026-07-01 generalization and UI reference refresh.
- The 2026-07-01 user instruction and working tree edit record the raw-source granularity and GitHub-search trigger update.

## Links

- [Project Overview](project-overview.md)
- [LLM Wiki Protocol Decision](llm-wiki-protocol-decision.md)
- [Promo Video](promo-video.md)

## Open Questions

- Should the PM-first operating sequence be represented in a compact diagram or table in README for faster external scanning?
- Should the skill include a lightweight packaging or lint script to enforce the distribution rules described in README?

## Change Notes

- 2026-07-01: Ingested generic AI product refinements and UI reference refresh from commits `95f18f1` and `607813f`; updated the operating model to emphasize AI responsibility-first design, Harness as product control layer, node-based Agent execution, compact/on-demand context, and UI as a workflow state machine.
- 2026-07-01: Added user-confirmed rules that broad raw source units can include the whole skill, whole project, and high-value conversation scope; clarified that larger raw records can live in separate `raw/` files; and recorded that brainstorming should proactively search GitHub prototypes under broader trigger conditions.
- 2026-06-30: Created from the main skill file, README, and reference set.
