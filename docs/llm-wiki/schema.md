# LLM Wiki Schema

## Scope

This wiki stores project-local knowledge for the `pm-skill` repository. It is not part of the distributable skill package. The skill directory keeps reusable operating instructions; this wiki keeps repository-specific sources, decisions, context, and open questions.

## Directory

```text
docs/llm-wiki/
├── index.md
├── log.md
├── schema.md
├── raw/
│   ├── sources.md
│   ├── conversations/
│   ├── external/
│   └── project-snapshots/
└── pages/
    ├── project-overview.md
    ├── pm-skill-operating-model.md
    ├── llm-wiki-protocol-decision.md
    ├── promo-video.md
    └── open-questions.md
```

Create new pages only when a topic has enough durable value to be read independently. Keep temporary command output, mechanical diffs, and low-confidence speculation out of wiki pages.

## Page Metadata

Pages under `pages/` should use YAML frontmatter:

```yaml
---
type: concept | entity | decision | source-summary | comparison | workflow | retrospective | evaluation | open-question | analysis
status: active | draft | disputed | superseded | archived
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources:
  - ../raw/sources.md#source-id
confidence: low | medium | high
tags: []
---
```

Use `status: disputed` or an explicit contradiction block when new sources challenge older claims. Do not silently overwrite old conclusions when the old conclusion may still matter by scope or date.

## Source Policy

- Register durable local sources in [raw/sources.md](raw/sources.md), including source ID, path, observation date, confidence, scope, and summary.
- Treat [raw/sources.md](raw/sources.md) as the source registry, not the only raw storage file. Longer sources, conversation summaries, external research sets, and project snapshots may live in separate `raw/` files and be referenced from the registry.
- For external sources referenced by local files, record the external URL and whether it was independently fetched or only cited by the local source.
- Do not store secrets, tokens, credentials, private customer data, or unredacted personal sensitive information.
- Avoid copying large raw source bodies into wiki pages. Summarize and link to stable paths instead.
- Transient repo state can be recorded only when it changes future action, and must be dated as an observation rather than treated as a timeless fact.

## Code Discovery Policy

- Prefer codebase-memory MCP for code discovery and structure queries before grep/glob/file search.
- Current indexed project name: `Users-lechuanwang-Desktop-pm-skill`.
- Index status observed on 2026-06-30: `ready`, with 166 nodes and 154 edges.
- This repository is mostly Markdown, SVG, static HTML, and media. codebase-memory is useful for section/file discovery, while direct file reads may still be needed for document content and static assets.
- Fall back to shell text search for non-code files, literal strings, configs, generated/static HTML, and cases where the graph does not expose enough content.

## Ingest Workflow

1. Read [index.md](index.md) first.
2. Identify source title, path or URL, provider, observed date, confidence, and scope.
3. Register or update [raw/sources.md](raw/sources.md); create a separate `raw/` file first when the source is too large or structured for a registry entry.
4. Update relevant pages with facts, decisions, corrections, links, and open questions.
5. Update [index.md](index.md) routing if a new page or important source changes task navigation.
6. Append [log.md](log.md) with touched pages, additions, conflicts, and deferred questions.

## Lint Workflow

For scoped lint after an ingest:

- Check that every page in [index.md](index.md) exists.
- Check that every `sources:` entry points to an entry in [raw/sources.md](raw/sources.md).
- Check that open questions remain dated and actionable.
- Check that page status, confidence, and update date are present.
- Check that claims with release or operational impact link to evidence.
- Add a lint entry to [log.md](log.md) when findings were fixed or deferred.
