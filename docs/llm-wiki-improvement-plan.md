# PM Skill 的 LLM Wiki 构建能力改进计划

Date: 2026-06-30
Source: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
Scope: pm-skill / project-local llm-wiki

## 改写结论

现有协议把 LLM Wiki 写得偏窄：它主要服务 AI 产品开发里的反思、踩坑、prompt/context、Agent Harness 和实现复盘。这个方向有价值，但不应该成为 `llm-wiki` 的 ingest 边界。

根据 Karpathy 的 LLM Wiki 模式，wiki 更像一个由 LLM 持续维护的 Markdown 知识层：raw sources 是事实来源，wiki pages 是被整理、交叉引用、持续更新的综合知识，schema/AGENTS/SKILL 负责约束 LLM 如何维护它。它可以吸收任何长期有价值的资料、观察、分析和用户确认，而不需要先被归类成“AI 产品反思”。

因此，本轮调整目标是：

1. 统一命名为 `llm-wiki`，默认路径为 `docs/llm-wiki/`，不再沿用旧的 AI 反思库命名。
2. 不为 ingest 设主题边界。任何有未来复用价值的 source、query result、用户纠正、产品判断、研究材料、源码理解、会议记录、竞品观察、错误复盘、实验结果都可以进入 wiki。
3. 把“反思记录”降级为 page type，而不是 wiki 的默认范围。
4. 保留上下文克制、按需读取、source provenance、冲突标记和不写 secrets 的质量约束。
5. 让协议更通用：它应该适用于产品、研究、业务、技术、团队协作、个人知识库等场景，而不是只服务 AI/SaaS 开发复盘。

## 从原文提炼出的核心模式

Karpathy 文档强调的不是“再做一个 RAG”，而是让 LLM 维护一个会复利增长的知识库：

- 新 source 进入后，LLM 不只是索引它，而是把关键信息编译进已有 wiki。
- 一个 source 可能同时更新 entity、concept、decision、comparison、timeline、open question 等多个页面。
- wiki 会随着每次 ingest、query、lint 变得更准确，而不是每次问答都从 raw documents 重新拼装。
- 人负责选择 source、提出问题、判断方向；LLM 负责总结、链接、归档、更新、标记冲突和维护索引。
- `index.md` 负责内容路由，`log.md` 负责时间线，schema/AGENTS/SKILL 负责维护规则。
- 小规模时先靠 Markdown、index 和 grep/search；规模变大再考虑搜索工具、MCP、Obsidian、qmd 或 embedding。

## 命名和目录原则

统一使用 `llm-wiki`：

- 路径：`docs/llm-wiki/`
- 标题：`LLM Wiki Index`、`LLM Wiki Log`
- 协议文件：`references/llm-wiki-protocol.md`
- 不再沿用旧的 AI 反思库路径或标题。

推荐的最小结构：

```text
docs/llm-wiki/
├── index.md
├── log.md
├── schema.md
├── raw/
│   └── sources.md
└── pages/
    └── ...
```

结构不要一次性铺满。项目只需要 `index.md` 和 `log.md` 时，就不要创建空目录；有 raw sources 需要登记时再加 `raw/`；有项目专属规则时再加 `schema.md`。

## Ingest 不设主题边界

新的规则应该明确：`llm-wiki` 的 ingest 边界不是“AI 产品开发”或“踩坑复盘”，而是“是否有长期价值”。

可以 ingest 的内容包括但不限于：

- 用户明确认可的产品判断、取舍、约束、目标用户、验收标准。
- 需求文档、会议记录、访谈、客户反馈、销售/客服信息、运营观察。
- 研究文章、论文、书籍章节、课程笔记、播客/视频摘要、外部网页。
- 竞品分析、市场观察、商业模式、定价、案例、尽调材料。
- 代码库理解、架构决策、接口契约、工具边界、部署经验、测试策略。
- Prompt/context/Agent Harness 决策、失败样例、评估标准、回归用例。
- 一次 query 产生的高价值比较表、综合分析、关系发现、open questions。
- 图片、截图、图表、设计稿、PDF、表格等资料的摘要和本地路径登记。
- 任何被用户指出“以后还会用到”的上下文。

不要把下面这些写进 wiki；这不是主题边界，而是质量和安全边界：

- secrets、token、密码、隐私数据、未脱敏个人敏感信息。
- 无长期价值的聊天噪声、一次性命令输出、机械 diff 复述。
- 未验证推测写成高置信事实。
- 整段聊天记录直接复制粘贴。
- LLM 无法追溯来源的重要事实。

## 三层架构

### Raw sources

Raw sources 是事实来源，可以是仓库里的文件，也可以是外部 URL、PDF、截图、会议纪要或用户提供的文本。LLM 可以读取和引用 raw，但不能静默改写 raw。

如果 source 本身存放在项目外，至少在 `raw/sources.md` 记录来源、日期、标题、位置、可信度和摘要。需要长期稳定引用时，优先保存一个可复现的本地快照或明确可访问路径。

### Wiki pages

Wiki pages 是 LLM 维护的 Markdown 知识层。它们不只是 source summary，还包括实体页、概念页、决策页、比较页、timeline、open questions、workflow、retrospective、evaluation log 等。

Wiki pages 可以被更新、重组和交叉引用。旧结论被新资料挑战时，不要静默覆盖；应标记 `superseded`、`disputed` 或写出 contradiction。

### Schema

Schema 是当前项目的 wiki 维护规则。它可以放在 `docs/llm-wiki/schema.md`，也可以由项目根目录 `AGENTS.md` 指向。Schema 应定义：

- 目录结构和命名约定。
- 页面类型和 frontmatter。
- source provenance 和引用方式。
- ingest、query、lint、write-back 工作流。
- 冲突处理规则。
- 什么内容禁止写入。

## 操作工作流

### Ingest

当用户提供新资料，或一次工作产生了长期有价值的信息时，执行 ingest。

推荐流程：

1. 识别 source：标题、来源、日期、作者/提供者、可信度、适用范围。
2. 登记 raw：保存 source 或在 `raw/sources.md` 登记路径/URL/摘要。
3. 读取 `index.md`，判断需要更新哪些已有页面；不要默认只新增一个孤立摘要。
4. 更新相关 pages：可能包括概念、实体、产品决策、竞品、架构、用户洞察、open questions 等。
5. 标记新增、修正、冲突、待确认问题和被替代结论。
6. 更新 `index.md` 的页面摘要和路由信息。
7. 追加 `log.md`，记录 ingest 发生了什么、触达哪些页面、留下哪些问题。

### Query

当用户问一个需要项目记忆的问题时，执行 query。

推荐流程：

1. 先读 `index.md`，再读相关页面和必要 raw source。
2. 回答时区分：wiki 已确认事实、当前推理、需要用户确认的问题。
3. 如果答案形成了新的综合、比较、决策、检查清单或 open questions，把它写回 wiki，或在回答中建议写回。
4. 追加 `log.md`，记录高价值 query 读取了什么、产出了什么、是否写回。

### Lint

周期性或重大 ingest 后，执行 scoped lint。

检查项：

- 是否有断链、孤立页面、重复页面、过期页面。
- 重要概念是否被多次提到但没有独立页面。
- 是否有新资料挑战旧结论但没有 contradiction。
- 页面是否缺少 source、更新时间、状态或置信度。
- `index.md` 是否落后于实际 pages。
- `open-questions.md` 是否长期无人处理。

Lint 默认是局部的：优先检查变更页面及其直接相邻页面。只有在用户明确要求、发布前、大批量 ingest 后，才做全量 lint。

## index.md 和 log.md 模板

`index.md` 回答“有什么”：

```markdown
# LLM Wiki Index

Use this wiki before planning, debugging, researching, answering project-memory questions, or summarizing reusable knowledge.

## Pages

- `pages/<page>.md`: 一句话说明页面内容、状态和主要来源。

## Recent High-Value Updates

- YYYY-MM-DD: 简述最近重要 ingest/query/lint 结果。

## Open Questions

- `pages/open-questions.md`: 尚未解决但可能影响判断的问题。

## Read Policy

Read only pages relevant to the current task. Start from this index, then follow links or source references as needed.
```

`log.md` 回答“发生过什么”：

```markdown
# LLM Wiki Log

## [2026-06-30] ingest | <source title>

- Source: `raw/...` or URL
- Touched pages: `pages/a.md`, `pages/b.md`
- Added:
- Updated:
- Conflicts:
- Open questions:

## [2026-06-30] query | <question>

- Read pages:
- Output:
- Filed back:

## [2026-06-30] lint | scoped

- Scope:
- Findings:
- Fixed:
- Deferred:
```

## 页面 metadata 和内容模板

重要页面建议使用 YAML frontmatter：

```yaml
---
type: concept | entity | decision | source-summary | comparison | workflow | retrospective | evaluation | open-question | analysis
status: active | draft | disputed | superseded | archived
created: 2026-06-30
updated: 2026-06-30
sources:
  - raw/sources.md#source-id
confidence: low | medium | high
tags:
  - product
  - research
---
```

正文建议包含：

```markdown
# <Page Title>

## Summary

这页当前确认了什么。

## Key Points

- 可复用的事实、判断或关系。

## Evidence

- Source links, raw paths, files, tests, user confirmations.

## Links

- Related pages.

## Open Questions

- 尚未确认但影响后续判断的问题。

## Change Notes

- YYYY-MM-DD: 新增/修正/被替代/冲突处理。
```

## 冲突处理

当新 source 挑战旧结论时，使用 contradiction 块，而不是静默覆盖：

```markdown
### Contradiction

Status: unresolved | resolved | accepted-contextual
Severity: soft | scope-mismatch | hard
New source:
Old claim:
Why it conflicts:
Resolution:
User decision:
```

处理原则：

- `soft`：可以共存，但需要写明条件差异。
- `scope-mismatch`：看似冲突，实则适用范围不同，需要补充边界。
- `hard`：直接矛盾，不能静默覆盖，需要用户确认或保留 unresolved。

## 与 PM Skill 的关系

`pm-skill` 仍然服务 PM-first 的 AI/SaaS 产品工作，但它不应该把 `llm-wiki` 限死在 AI 产品复盘里。

新的定位是：

- Skill 只保存 LLM Wiki 的维护协议，不保存具体项目知识。
- 具体项目知识写在当前项目的 `docs/llm-wiki/`。
- Reflection、pitfall、release retrospective 都只是 page type。
- Ingest 范围由“长期价值”判断，不由主题预设边界判断。
- 对小项目保持轻量，先用 Markdown、index、log；规模上来再加搜索或 MCP。

## 最小落地版本

本轮已按这个范围落地：

1. 把项目 wiki 路径统一为 `docs/llm-wiki/`。
2. 把 wiki 标题统一为 `LLM Wiki Index/Log`。
3. 重写 `llm-wiki-protocol.md`，明确 no topic boundary ingest。
4. 在 `SKILL.md` 中把 “LLM Wiki 反思” 改成 “LLM Wiki 知识层”。
5. 在 README 中把 wiki 描述从“记录踩坑经验”扩展为“维护项目知识层”。
6. 保留安全和质量约束：不写 secrets、不写噪声、不把未验证推测写成事实。
7. 增加写回权限策略，区分可直接写、应先确认和不应写回的情况。
8. 增加 source acquisition 边界，避免把“任何有价值都可 ingest”误解为自动收集外部资料。
9. 将开源项目借鉴记录接入 `docs/llm-wiki/`，区分 source 登记、analysis、comparison 和 decision。
10. 增加最小初始化模板，只创建 `index.md` 和 `log.md`，避免提前铺满空页面。
11. 增加 skill 分发检查，避免 `.DS_Store`、`.Rhistory`、`.env`、日志、草稿和项目私有知识进入 skill 包。

完成后，PM skill 的 wiki 能力会从“可复用反思记录”升级为“通用、持续增长、可维护的项目知识系统”。
