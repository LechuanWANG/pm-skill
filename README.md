<div align="center">
  <h3><em>The PM-First AI Product Skill for Codex Agents</em></h3>

  <a href="./ai-product-pm-style/SKILL.md">
    <img src="./ai-product-pm-style/assets/ai-product-pm-style.svg" alt="AI Product PM Style Skill" width="112">
  </a>

  <p>
    <a href="./ai-product-pm-style/SKILL.md">
      <img alt="Open Skill" src="https://img.shields.io/badge/OPEN-SKILL-111827?style=for-the-badge&labelColor=374151">
    </a>
    <a href="#install">
      <img alt="Install" src="https://img.shields.io/badge/INSTALL-%24skill--installer-A855F7?style=for-the-badge&labelColor=111827">
    </a>
  </p>

  <p>
    <strong>Portable Codex skill for AI/SaaS product work:</strong> PM-first brainstorming, API and Agent architecture,
    prompt discipline, Harness constraints, modular implementation, clean UI copy, and GitHub prototype research.
  </p>

  <p>
    <a href="https://github.com/LechuanWANG/ai-product-pm-style/stargazers">
      <img alt="GitHub Stars" src="https://img.shields.io/github/stars/LechuanWANG/ai-product-pm-style?style=for-the-badge&logo=github&label=STARS&labelColor=374151&color=6B7280">
    </a>
    <a href="./ai-product-pm-style/references/open-source-ideas.md">
      <img alt="Prototype Notes" src="https://img.shields.io/badge/GITHUB-PROTOTYPE%20NOTES-0F766E?style=for-the-badge&labelColor=111827">
    </a>
    <a href="./ai-product-pm-style/agents/openai.yaml">
      <img alt="Skill Metadata" src="https://img.shields.io/badge/METADATA-openai.yaml-F59E0B?style=for-the-badge&labelColor=111827">
    </a>
  </p>

  <p>
    <a href="#design-principles">
      <img alt="Tools" src="https://img.shields.io/badge/TOOLS-CODEX%20%C2%B7%20GITHUB-111827?style=for-the-badge&labelColor=1F2937">
    </a>
    <a href="./ai-product-pm-style/SKILL.md#ai-%E4%BA%A7%E5%93%81%E6%9E%B6%E6%9E%84%E5%81%8F%E5%A5%BD">
      <img alt="Focus" src="https://img.shields.io/badge/FOCUS-AGENT%20%C2%B7%20HARNESS-2563EB?style=for-the-badge&labelColor=111827">
    </a>
    <a href="#design-principles">
      <img alt="Style" src="https://img.shields.io/badge/STYLE-PM--FIRST-10B981?style=for-the-badge&labelColor=111827">
    </a>
  </p>
</div>

# AI Product PM Style Skill

一个面向 Codex 的个人产品经理风格 skill，用来让 AI 在做 AI/SaaS 产品 brainstorming、方案设计、功能实现和实现后解释时，更贴近产品经理视角，而不是只从代码视角推进。

这个 skill 特别适合以下场景：

- 设计 AI SaaS 产品、API-backed AI 功能或 Agent 工作流
- 规划 LangChain、LangGraph 或类似 Agent orchestration 架构
- 控制 system prompt、user prompt 和上下文预算
- 用 Harness 思想约束 AI 输入、输出、工具边界和校验点
- 做重大产品更新前的需求澄清、方案拆解和阶段计划
- 从 GitHub prototype 或开源项目里提炼可借鉴的技术特点
- 写完代码后，用 PM 能理解的方式解释产品结果、架构变化和风险

## Skill Contents

```text
ai-product-pm-style/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── assets/
│   ├── ai-product-pm-style.svg
│   └── ai-product-pm-style-small.svg
└── references/
    └── open-source-ideas.md
```

## Install

Use Codex's `$skill-installer` with the GitHub directory URL:

```text
$skill-installer install https://github.com/LechuanWANG/ai-product-pm-style/tree/main/ai-product-pm-style
```

Or install by repo and path:

```text
$skill-installer install ai-product-pm-style from LechuanWANG/ai-product-pm-style
```

After installing, restart Codex so it can pick up the new skill.

## Usage Examples

```text
Use $ai-product-pm-style 帮我 brainstorm 一个面向销售团队的 AI 客户摘要功能。
```

```text
Use $ai-product-pm-style 评审这个 Agent 工作流，看 prompt、context 和 Harness 约束有没有问题。
```

```text
Use $ai-product-pm-style 帮我基于 GitHub 上类似 prototype 的技术特点，设计一个可落地的 AI SaaS 功能方案。
```

```text
Use $ai-product-pm-style 按我的产品风格解释你刚刚实现的代码改动。
```

## Design Principles

- 产品逻辑先于代码细节。
- Prompt 和上下文要克制，不盲目堆砌。
- Harness 要明确输入、输出、工具边界、校验点和失败处理。
- 鼓励技术性创新，但要先用 prototype 或小范围实现验证。
- 主动从 GitHub prototype 和开源项目中提炼技术特点、架构模式和工程组织方式。
- 代码结构要清晰、模块化、便于后续产品迭代。
- UI 要简约、好看、切题，文案要短、准、具体。

## Open Source Research Notes

When a task borrows from GitHub projects or public prototypes, use `references/open-source-ideas.md` as the note-taking format. It records:

- source project links
- license and observed date
- borrowable technical ideas
- product implications
- dependency, license, and security risks

## Repository Format

This repository follows the common Codex skill distribution pattern: the skill is a self-contained folder with `SKILL.md`, `agents/openai.yaml`, optional `assets/`, and optional `references/`. The root README explains installation and usage, while the executable skill instructions live inside `ai-product-pm-style/SKILL.md`.
