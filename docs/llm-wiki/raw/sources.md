# Raw Sources

## repo-readme

- Title: PM Skill repository README
- Location: `README.md`
- Provider: repository
- Observed: 2026-07-01
- Confidence: high
- Scope: Product positioning, installation, usage examples, distribution format, progressive references, and release hygiene.
- Summary: Describes `pm-skill` as a personal Codex skill for PM-first AI product work, with bilingual documentation, `$skill-installer` install commands, intro video link, repository structure, progressive reference routing, AI responsibility/Harness/context/UI principles, and distribution checks.

## skill-main

- Title: PM Skill main instruction file
- Location: `pm-skill/SKILL.md`
- Provider: repository
- Observed: 2026-07-01
- Confidence: high
- Scope: Skill trigger behavior, PM-first principles, reference routing, work mode, LLM Wiki policy, and output style.
- Summary: Defines the product-first operating order for AI products: user flow, AI responsibility, Agent need, Harness boundary, context strategy, prompt strategy, Agent/tool strategy, product UI, and evaluation. It also defines reference routing, the rule that project-specific long-term memory belongs in `docs/llm-wiki/`, and the rule that raw sources can be scoped at file, skill, project snapshot, repository-history, or high-value conversation granularity. It now clarifies that `raw/sources.md` is a registry and longer source records can live in separate `raw/` files.

## skill-reference-set

- Title: PM Skill reference set
- Location: `pm-skill/references/*.md`
- Provider: repository
- Observed: 2026-07-01
- Confidence: high
- Scope: Brainstorming, prompt/context design, Agent Harness, UI production, implementation summary, open-source research notes, and LLM Wiki protocol.
- Summary: Provides task-specific operating details that the main skill routes to on demand, including AI responsibility-first planning, proactive GitHub prototype search during brainstorming, Harness constraints, compact/on-demand context, node-based Agent execution, concrete UI baseline rules, open-source idea recording, and LLM Wiki maintenance.

## llm-wiki-protocol

- Title: LLM Wiki protocol
- Location: `pm-skill/references/llm-wiki-protocol.md`
- Provider: repository
- Observed: 2026-07-01
- Confidence: high
- Scope: Wiki directory, ingest/query/lint workflows, page template, write-back policy, source acquisition, and conflict handling.
- Summary: Defines the canonical maintenance protocol for project-local LLM Wikis, including the current decision that raw sources can be single files, directories, whole skill directories, whole project snapshots, repository history slices, external search result sets, or high-value portions of the current conversation when scope and provenance are explicit. It also defines `raw/sources.md` as a registry rather than the only raw storage file.

## conversation-2026-07-01-raw-and-github-search

- Title: User confirmation on raw-source granularity and GitHub prototype search
- Location: current conversation on 2026-07-01; summarized in `raw/conversations/2026-07-01-skill-rule-updates.md`
- Provider: user instruction
- Observed: 2026-07-01
- Confidence: high for user intent; medium for future behavioral impact until exercised on real brainstorm tasks.
- Scope: Skill rule update request for LLM Wiki raw source granularity and brainstorming-stage GitHub prototype search triggers.
- Summary: User stated that for raw sources, the whole skill, the whole project, and the conversation can be treated as raw. User also clarified that raw ingests can use new files under `raw/` instead of squeezing all content into `raw/sources.md`. User judged that the skill's brainstorming stage had too weak a motive/probability for proactively searching GitHub for similar product directions, and asked to modify wording or add conditions to make that trigger more likely.

## workspace-edit-2026-07-01-raw-github-trigger

- Title: Local skill edit for raw source granularity and proactive GitHub prototype search
- Location: working tree diff on `pm-skill/SKILL.md`, `pm-skill/references/llm-wiki-protocol.md`, `pm-skill/references/brainstorming.md`, and `pm-skill/references/open-source-ideas.md`
- Provider: current workspace
- Observed: 2026-07-01
- Confidence: high for local file contents; commit hash pending until changes are committed.
- Scope: Uncommitted local changes that add broad raw source granularity rules and stronger proactive GitHub prototype search triggers.
- Summary: Main skill now names single files, whole skill directories, whole project snapshots, repository history slices, and high-value conversation portions as possible raw sources. The LLM Wiki protocol defines how to register broad raw sources without copying full contents and allows separate files under `raw/` for longer source records. Brainstorming now defaults to considering GitHub prototype search for new AI products, major features, Agent/RAG/workflow, UI patterns, and uncertain tech stacks, while `open-source-ideas.md` defines search, filtering, and recording steps.

## llm-wiki-improvement-plan

- Title: PM Skill 的 LLM Wiki 构建能力改进计划
- Location: `docs/llm-wiki-improvement-plan.md`
- External reference cited by source: `https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f`
- Provider: repository
- Observed: 2026-06-30
- Confidence: high for local project decisions; medium for external-source interpretation unless the external gist is separately fetched or snapshotted.
- Scope: Rationale and implementation plan for broadening `llm-wiki` from AI reflection notes into a general LLM-maintained project knowledge layer.
- Summary: Establishes the rename to `llm-wiki`, the `docs/llm-wiki/` path, long-term-value ingest boundary, source provenance, minimal Markdown-first structure, and relationship to `pm-skill`.

## skill-metadata

- Title: OpenAI skill metadata
- Location: `pm-skill/agents/openai.yaml`
- Provider: repository
- Observed: 2026-07-01
- Confidence: high
- Scope: Display metadata, icons, brand color, default prompt, and implicit invocation policy.
- Summary: Sets display name to "PM Skill", short description to "PM-first AI product work with Harness and LLM Wiki memory", brand color to `#77726B`, icon paths to the refreshed `assets/` SVGs, and `allow_implicit_invocation: true`.

## commit-95f18f1

- Title: Refine generic AI product PM skill
- Location: git commit `95f18f1`
- Provider: repository history
- Observed: 2026-07-01
- Confidence: high
- Scope: Generic AI product positioning, README examples, main skill sequence, Agent Harness reference, brainstorming reference, prompt/context reference, UI production reference, and release hygiene.
- Summary: Generalized the skill from AI/SaaS wording toward broader AI product work; added the explicit sequence of AI responsibility before Agent choice; strengthened Harness as the control layer for inputs, outputs, tools, permissions, transitions, validation, fallback, and persistence; introduced the `analyze -> decide -> retrieve -> generate -> validate -> persist` execution split; reinforced compact/on-demand retrieval; and added `.obsidian/` to `.gitignore`.

## commit-607813f

- Title: Refresh skill UI style and reference
- Location: git commit `607813f`
- Provider: repository history
- Observed: 2026-07-01
- Confidence: high
- Scope: Skill SVG assets, OpenAI metadata brand color, and UI production reference specificity.
- Summary: Refreshed the skill visual identity toward a blocky, high-contrast, retro/monospace PM Skill style with neutral brand color `#77726B`; updated large and small SVG assets; and expanded `pm-skill/references/ui-production.md` with concrete UI baseline, review output, interaction, motion/performance, typography/layout, accessibility, mobile, and verification rules.

## ui-skills-baseline-reference

- Title: ibelick/ui-skills baseline UI skill
- Location: `https://github.com/ibelick/ui-skills/blob/main/skills/baseline-ui/SKILL.md`
- Provider: public GitHub repository
- Observed: 2026-07-01
- Confidence: medium-high because the public GitHub file can change after observation.
- Scope: Public UI skill structure and rule style used as inspiration for making `pm-skill/references/ui-production.md` more concrete.
- Summary: The public UI skill reference influenced the local UI reference at the level of checklist structure and practical rule specificity. The `pm-skill` UI reference remains a generic AI product UI reference and does not copy project-specific implementation details.

## promo-composition-project

- Title: AI PM Skill promo HyperFrames project
- Location: `ai-pm-skill-promo/`
- Provider: local workspace
- Observed: 2026-06-30
- Confidence: medium-high for local content; confirm tracking status before release decisions.
- Scope: Promo video source, design direction, HyperFrames commands, composition HTML, metadata, assets, fonts, and rendered MP4.
- Summary: Contains a HyperFrames composition for an 18-second PM Skill promotional video, with `index.html`, `DESIGN.md`, `AGENTS.md`, `CLAUDE.md`, `package.json`, `hyperframes.json`, `meta.json`, SVG assets, font subsets, and `renders/ai-pm-skill-promo.mp4`.

## repo-inspection-2026-06-30

- Title: Repository inspection on 2026-06-30
- Location: local shell and codebase-memory observations
- Provider: current workspace
- Observed: 2026-06-30
- Confidence: medium because working tree state can change.
- Scope: Current file layout, codebase-memory index status, tracked file list, and release-relevant local observations.
- Summary: `docs/llm-wiki/` did not exist before this ingest. codebase-memory project `Users-lechuanwang-Desktop-pm-skill` was ready with 166 nodes and 154 edges. `git ls-files` showed the skill files, README, `docs/llm-wiki-improvement-plan.md`, and rendered promo MP4 as tracked. Local inspection also showed untracked promo source files and ignored local files such as `.DS_Store` and `.Rhistory`.
