# LLM Wiki 反思协议

## 目标

使用项目内 LLM Wiki 记录 AI 产品开发中的可复用经验，避免重复踩坑。这个文件只定义方法；真实知识库必须放在当前项目文档中，默认路径是 `docs/ai-wiki/`，不要写入 skill 目录。

## 默认项目结构

当任务足够重大且项目还没有 wiki 时，在当前项目内创建：

```text
docs/ai-wiki/
├── index.md
├── product-decisions.md
├── prompt-context-pitfalls.md
├── agent-harness-pitfalls.md
├── implementation-pitfalls.md
├── ui-copy-lessons.md
└── release-retrospectives.md
```

只创建当前任务需要的页面。不要为了完整目录而创建空文件。

## 读取规则

开始以下任务前，如果 `docs/ai-wiki/index.md` 存在，先读取索引，再只读取相关页面：

-   重大 AI 产品功能、产品架构、数据流或核心用户流程设计。
-   Agent workflow、tool contract、权限、状态、fallback 或校验机制调整。
-   prompt、context、schema、retrieval、evaluation 或输出稳定性调整。
-   曾经失败过、用户特别纠正过，或明显可能重复踩坑的实现任务。
-   发布、部署、回归、验收或线上问题复盘。

不要默认读取整个 wiki。用索引选择页面，避免把无关项目记忆塞进当前上下文。

## 写入触发

在以下情况下更新项目内 wiki：

-   一个 bug、测试失败或集成问题需要非显然推理才解决。
-   AI 行为问题涉及 prompt、context、schema、工具调用、Agent 状态或评估方式。
-   用户纠正了重要产品方向、交互判断、文案风格或验收标准。
-   发现一个以后会复用的架构、Harness、验证或调试模式。
-   发现一个失败方案很容易被下次重复尝试。
-   完成一次重大功能后，有明确的后续预防检查点。

不要为简单文案、单行样式、机械重命名、确定性命令或无复用价值的小 bug 写反思。

## 写入格式

优先更新已有页面，不要频繁创建碎片化页面。每条记录用这个结构：

```markdown
## <短标题>

Date: YYYY-MM-DD
Tags: prompt, context, agent, harness, ui, implementation, deployment, evaluation
Scope: project-specific | reusable | global-candidate
Confidence: low | medium | high

### Problem Signature

下次如何识别同类问题。写具体信号，不写泛泛感受。

### Context

当时在做什么产品、功能、架构或流程。

### Root Cause

真正原因是什么。不要只写“代码有 bug”或“prompt 不好”。

### Fix Pattern

这次有效的修复方式是什么。

### Prevention Checklist

下次开始类似任务前要检查什么。

### Applicability Boundary

什么时候适用，什么时候不要套用。

### Evidence

相关文件、测试、用户反馈、日志或验证结果。
```

## index.md 模板

项目内 `docs/ai-wiki/index.md` 用来路由，不要写成长文：

```markdown
# AI Wiki Index

Use this wiki before planning, debugging, or summarizing non-trivial AI product work.

## Pages

- `product-decisions.md`: 已确认的产品方向、目标用户、不可变约束和重要取舍。
- `prompt-context-pitfalls.md`: prompt 过长、上下文污染、schema 不清、few-shot 滥用、输出不稳定。
- `agent-harness-pitfalls.md`: Agent 工具边界、权限、校验、fallback、状态管理、循环调用。
- `implementation-pitfalls.md`: 目录结构、模块拆分、依赖、测试、部署、环境问题。
- `ui-copy-lessons.md`: UI 文案、主次操作、AI 输出呈现、用户确认流程。
- `release-retrospectives.md`: 发布、验证、线上问题、复盘结论。

## Read Policy

Read only pages relevant to the current task. Do not load the whole wiki by default.

## Write Policy

Write only reusable lessons. Prefer updating existing pages over creating new ones.
```

## 质量标准

-   记录必须能改变下次行动，不能只是“以后注意”。
-   保留适用边界，避免把项目特有结论误当通用原则。
-   不要记录 secrets、token、私密用户数据、未验证猜测或一次性日志噪声。
-   如果一条经验连续跨项目复用，再考虑把它提炼为 skill 的通用规则。
-   如果 wiki 内容和用户的新指令冲突，以用户新指令为准，并更新项目 wiki 中过时的记录。
