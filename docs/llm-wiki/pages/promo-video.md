---
type: source-summary
status: active
created: 2026-06-30
updated: 2026-06-30
sources:
  - ../raw/sources.md#promo-composition-project
  - ../raw/sources.md#repo-readme
  - ../raw/sources.md#repo-inspection-2026-06-30
confidence: medium
tags:
  - hyperframes
  - promo
  - video
---

# Promo Video

## Summary

`ai-pm-skill-promo/` contains a HyperFrames project for an 18-second promotional video introducing PM Skill. README embeds or links the rendered MP4 at `ai-pm-skill-promo/renders/ai-pm-skill-promo.mp4`.

## Key Points

- Composition format: static HyperFrames HTML with GSAP timeline registration on `window.__timelines["main"]`.
- Output duration: 18 seconds.
- Canvas: 1920 x 1080, `zh-CN`.
- Core message: move from simply using AI to delivering AI products with product judgment, Harness boundaries, context control, and verification.
- Scene 1 theme: PM-first operating system. It emphasizes product flow, context restraint, and verifiable results.
- Scene 2 theme: Harness over prompt sprawl. It frames AI control through structured input, context budget, small tool contracts, schema/failure formats, deterministic checks, and fallback.
- Scene 3 theme: product result. It connects MVP flow, Agent Harness, prompt/context control, review, verification, and reusable retrospectives.
- Visual direction: premium consulting-style strategy deck in motion, warm ivory/paper surface, deep ink, consulting green, muted brass, precise typography, restrained rules, and subtle data structures.
- Local assets include SVG marks, three font subsets, and the rendered MP4.

## Maintenance Notes

- For any future HyperFrames work, use the HyperFrames-specific skill before editing composition files.
- After changing any `.html` composition, run `npm run check` from `ai-pm-skill-promo/`.
- Relevant scripts in `ai-pm-skill-promo/package.json`: `dev`, `check`, `render`, and `publish`.
- HyperFrames rules from `ai-pm-skill-promo/AGENTS.md` include timed elements needing `data-start`, `data-duration`, `data-track-index`, and `class="clip"`; timelines must be paused and registered; logic should stay deterministic.
- Tracking status needs confirmation before release: local inspection on 2026-06-30 showed the rendered MP4 tracked while the promo source files appeared untracked.

## Evidence

- `README.md` links the rendered video.
- `ai-pm-skill-promo/DESIGN.md` defines visual language, colors, typography, motion, and anti-patterns.
- `ai-pm-skill-promo/AGENTS.md` defines HyperFrames commands and validation requirements.
- `ai-pm-skill-promo/index.html` contains the 18-second three-scene composition and GSAP timeline.
- `ai-pm-skill-promo/package.json` defines local HyperFrames commands.
- `ai-pm-skill-promo/hyperframes.json` defines registry and asset paths.

## Links

- [Project Overview](project-overview.md)
- [PM Skill Operating Model](pm-skill-operating-model.md)
- [Open Questions](open-questions.md)

## Open Questions

- Should `ai-pm-skill-promo/` source files be committed for reproducible video edits, or should the repository intentionally track only the rendered MP4?
- Should the promo project get a short README explaining how to regenerate `renders/ai-pm-skill-promo.mp4`?

## Change Notes

- 2026-06-30: Created from local promo project files and README.
