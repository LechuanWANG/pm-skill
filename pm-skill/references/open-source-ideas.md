# 开源项目借鉴记录

用于 GitHub 项目、开源 prototype、开源库和公开实现方案的产品化借鉴。

## 写入位置

-   Source 登记：`docs/llm-wiki/raw/sources.md`，记录链接、license、查看日期、摘要和可信度。
-   长期分析：`docs/llm-wiki/pages/`，使用 `source-summary`、`comparison`、`decision` 或 `analysis` 页面。
-   一次性查阅：在当前任务中引用即可。

## 记录模板

```markdown
# 开源项目借鉴：<功能或方向>

## Sources

| 项目 | 链接 | License | 查看日期 | 参考价值 |
| --- | --- | --- | --- | --- |
| <名称> | <URL> | <许可证> | <YYYY-MM-DD> | <产品或架构价值> |

## Ideas

### <思路名称>

- 产品价值：
- 技术特点：
- 架构模式：
- 适配方式：
- 采用前验证：

## Product Impact

- 用户体验：
- AI 行为：
- Prompt/context：
- Evaluation：
- 工程结构：
- 依赖、license、安全风险：

## Decision

- 推荐：
- 下一步：
- 风险：
```

## 记录规则

-   记录可复用 idea、来源、适用边界和验证项。
-   区分“借鉴思路”和“直接引入依赖”。
-   直接复用代码或依赖前，记录 license、维护状态、兼容性、安全风险和项目适配成本。
-   对可复用分析，同步更新 `docs/llm-wiki/index.md` 和 `docs/llm-wiki/log.md`。
