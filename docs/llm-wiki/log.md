# LLM Wiki Log

## [2026-06-30] init | project wiki

- Created: `index.md`, `log.md`, `schema.md`, `raw/sources.md`, and initial pages under `pages/`.
- Purpose: Establish project-local memory for the `pm-skill` repository and make future PM-first skill, LLM Wiki, release, and promo work easier to route.
- Open questions: See `pages/open-questions.md`.

## [2026-06-30] ingest | PM Skill repository baseline

- Source: `README.md`, `pm-skill/SKILL.md`, `pm-skill/references/*.md`, `pm-skill/agents/openai.yaml`, `docs/llm-wiki-improvement-plan.md`, `ai-pm-skill-promo/*`, local git/file inspection, and codebase-memory index status.
- Touched pages: `pages/project-overview.md`, `pages/pm-skill-operating-model.md`, `pages/llm-wiki-protocol-decision.md`, `pages/promo-video.md`, `pages/open-questions.md`, `schema.md`, `raw/sources.md`.
- Added: Repository purpose, distribution model, PM-first operating model, LLM Wiki decision, source registry, HyperFrames promo summary, and current open questions.
- Updated: None; this was the first wiki ingest.
- Conflicts: None found in the ingested source set.
- Open questions: Promo source tracking, external provenance handling for the Karpathy-linked improvement plan, and release hygiene around ignored local files.

## [2026-06-30] lint | scoped initialization

- Scope: Initial wiki files, source IDs, page frontmatter, and index routing.
- Findings: Expected Markdown files exist; source IDs referenced by pages are registered in `raw/sources.md`; page frontmatter includes type, status, created, updated, and confidence.
- Fixed: None required after the deterministic scoped check.
- Deferred: Ignored `.DS_Store` metadata exists locally under `docs/llm-wiki/` but is not part of wiki content or tracked release material.

## [2026-07-01] ingest | generic AI product operating model and UI reference refresh

- Source: `README.md`, `pm-skill/SKILL.md`, `pm-skill/references/*.md`, `pm-skill/agents/openai.yaml`, git commits `95f18f1` and `607813f`, and the public `ibelick/ui-skills` baseline UI reference URL.
- Touched pages: `raw/sources.md`, `pages/pm-skill-operating-model.md`, `pages/project-overview.md`, `pages/open-questions.md`, and `index.md`.
- Added: Source entries for the two 2026-07-01 commits and the public UI baseline reference; current wiki summary of generic AI product positioning, AI responsibility-first planning, Harness as product control layer, node-based Agent execution, compact/on-demand context, UI workflow-state expectations, refreshed visual identity, and more concrete UI production rules.
- Updated: Existing source observations for README, main skill, reference set, and metadata; project overview wording from AI/SaaS toward AI products; metadata brand color to `#77726B`; release hygiene evidence for `.obsidian/` ignore coverage.
- Conflicts: None found. The update intentionally keeps the operating model generic for all AI products and excludes project-specific business details from reusable skill knowledge.
- Open questions: Promo source tracking and automated packaging guard remain unresolved.

## [2026-07-01] ingest | raw-source granularity and GitHub prototype trigger update

- Source: User instruction in the current conversation and local working tree changes to `pm-skill/SKILL.md`, `pm-skill/references/llm-wiki-protocol.md`, `pm-skill/references/brainstorming.md`, and `pm-skill/references/open-source-ideas.md`.
- Touched pages: `raw/sources.md`, `raw/conversations/2026-07-01-skill-rule-updates.md`, `pages/pm-skill-operating-model.md`, `pages/llm-wiki-protocol-decision.md`, `schema.md`, and `index.md`.
- Added: Source entries for the user-confirmed rule change and local skill edit; a dedicated raw conversation summary file; wiki summary that raw sources can include whole skill, whole project snapshot, repository history slice, external search result set, and high-value conversation scope under explicit provenance and privacy boundaries.
- Updated: Operating model now records proactive GitHub prototype/open-source search as a default brainstorming consideration for new AI products, major features, Agent/RAG/workflow, UI patterns, and uncertain technical directions.
- Updated: LLM Wiki protocol and schema now clarify that `raw/sources.md` is a registry, not the only raw storage file; larger source records may live in separate `raw/` files.
- Conflicts: None found. The broader raw source model keeps the long-term-value, privacy, authorization, and confidence checks intact.
- Open questions: Future real brainstorm tasks should confirm whether these triggers increase actual GitHub search usage without over-searching low-value local edits.

## [2026-07-01] lint | skill and wiki update scope

- Scope: `pm-skill/` edits and `docs/llm-wiki/` ingest/update files.
- Findings: `quick_validate.py pm-skill` passed; `git diff --check -- pm-skill docs/llm-wiki` passed; source IDs for the conversation and local edit are registered and referenced by relevant pages.
- Guardrail check: No project-specific business terms from the user's separate AI product project were found in the generic skill files or the newly updated reusable wiki pages.
- Deferred: Ignored local files under `docs/llm-wiki/` such as `.DS_Store`, `.Rhistory`, and `.obsidian/` remain local metadata and are excluded by `.gitignore`; they are not part of the wiki content set.
