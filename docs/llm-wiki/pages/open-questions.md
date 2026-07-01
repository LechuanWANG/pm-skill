---
type: open-question
status: active
created: 2026-06-30
updated: 2026-07-01
sources:
  - ../raw/sources.md#repo-readme
  - ../raw/sources.md#llm-wiki-improvement-plan
  - ../raw/sources.md#promo-composition-project
  - ../raw/sources.md#repo-inspection-2026-06-30
  - ../raw/sources.md#commit-95f18f1
confidence: medium
tags:
  - open-questions
  - release
  - provenance
---

# Open Questions

## Summary

These questions are not blockers for normal skill use, but they may affect release quality, provenance, or future maintainability.

## Questions

### Promo source tracking

- Question: Should `ai-pm-skill-promo/` source files be tracked, or is the intended release artifact only `ai-pm-skill-promo/renders/ai-pm-skill-promo.mp4`?
- Why it matters: The rendered MP4 can be published without source, but future edits and reproducible rendering require the composition source, design file, metadata, assets, and package scripts.
- Current evidence: Local inspection on 2026-06-30 showed `ai-pm-skill-promo/renders/ai-pm-skill-promo.mp4` tracked and several promo source files untracked.
- Status: unresolved.

### External LLM Wiki provenance

- Question: Should the Karpathy gist cited by `docs/llm-wiki-improvement-plan.md` be snapshotted or summarized as a raw external source if future work depends on it directly?
- Why it matters: The local improvement plan is enough for current repository decisions, but external-source claims have better provenance if the source is fetched, dated, and summarized directly.
- Current evidence: `docs/llm-wiki-improvement-plan.md` cites `https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f`.
- Status: unresolved.

### Release packaging guard

- Question: Should the repository add a small deterministic check that validates the distributable `pm-skill/` directory contains only intended files?
- Why it matters: README already documents the release rule, but an automated check would reduce the risk of `.DS_Store`, `.Rhistory`, `.env`, logs, drafts, temporary files, or project-local wiki knowledge entering the packaged skill.
- Current evidence: README includes manual distribution checks; `.gitignore` excludes common local/private files and now includes `.obsidian/` after commit `95f18f1`.
- Status: unresolved.

### ADR versus wiki decision page

- Question: Should repository-level decisions also be recorded through codebase-memory ADR support, or is `docs/llm-wiki/pages/llm-wiki-protocol-decision.md` sufficient for this small documentation-first repository?
- Why it matters: codebase-memory reported no ADR present. The wiki page is probably enough now, but ADRs may help if architecture decisions grow beyond docs.
- Current evidence: codebase-memory schema inspection on 2026-06-30 reported `adr_present: false`.
- Status: unresolved.

## Links

- [Project Overview](project-overview.md)
- [LLM Wiki Protocol Decision](llm-wiki-protocol-decision.md)
- [Promo Video](promo-video.md)

## Change Notes

- 2026-07-01: Updated release packaging evidence after `.obsidian/` was added to `.gitignore`; the automated packaging guard question remains unresolved.
- 2026-06-30: Created during initial wiki ingest.
