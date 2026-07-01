---
type: entity
status: active
created: 2026-06-30
updated: 2026-07-01
sources:
  - ../raw/sources.md#repo-readme
  - ../raw/sources.md#skill-main
  - ../raw/sources.md#skill-metadata
  - ../raw/sources.md#repo-inspection-2026-06-30
  - ../raw/sources.md#commit-95f18f1
  - ../raw/sources.md#commit-607813f
confidence: high
tags:
  - project
  - distribution
  - codex-skill
---

# Project Overview

## Summary

This repository distributes `pm-skill`, a Codex skill for PM-first AI product work. The stable package is the `pm-skill/` directory; project-specific memory lives outside that package in `docs/llm-wiki/`.

## Key Points

- Primary product: a reusable Codex skill that makes AI product work start from user flow, product outcome, AI responsibility, Harness boundaries, context strategy, prompt strategy, Agent/tool strategy, product UI, and evaluation.
- Target use cases include AI product brainstorming, API-backed AI features, Agent workflow design, LangChain/LangGraph-style orchestration planning, prompt/context control, Harness review, GitHub prototype research, UI production guidance, and project-local LLM Wiki maintenance.
- Install surface in README uses `$skill-installer` with either a GitHub directory URL or repo/path syntax.
- Main distributable layout is `pm-skill/SKILL.md`, `pm-skill/agents/openai.yaml`, `pm-skill/assets/`, and `pm-skill/references/`.
- Metadata in `pm-skill/agents/openai.yaml` sets the display name, icon paths, brand color `#77726B`, default prompt, and `allow_implicit_invocation: true`.
- Skill visual assets in `pm-skill/assets/` now use a blocky PM Skill visual style with dark borders, neutral/off-white tones, offset shadow treatment, and compact monospace-like cues.
- README explicitly says project memory belongs in the consuming project's `docs/llm-wiki/`, not inside the skill directory.
- Distribution checks should confirm that `.DS_Store`, `.Rhistory`, `.env`, logs, temporary output, drafts, and project-private knowledge do not enter the packaged skill.

## Evidence

- `README.md` describes positioning, use cases, install commands, repository format, progressive references, and distribution checks.
- `pm-skill/SKILL.md` defines the executable skill instructions and reference routing.
- `pm-skill/agents/openai.yaml` defines display metadata and implicit invocation policy.
- Git commits `95f18f1` and `607813f` record the 2026-07-01 positioning and UI identity/reference updates.
- Local inspection on 2026-06-30 found ignored local files and untracked promo source files; treat this as release-relevant dated context, not a timeless fact.

## Links

- [PM Skill Operating Model](pm-skill-operating-model.md)
- [LLM Wiki Protocol Decision](llm-wiki-protocol-decision.md)
- [Promo Video](promo-video.md)
- [Open Questions](open-questions.md)

## Open Questions

- Should the promo source project be tracked or intentionally remain local while only the rendered MP4 is tracked?
- Should release prep include an automated packaging check for the skill directory?

## Change Notes

- 2026-07-01: Updated repository overview after generic AI product positioning, UI reference expansion, brand color change to `#77726B`, and refreshed skill SVG assets.
- 2026-06-30: Created from repository README, skill metadata, main skill file, and local inspection.
