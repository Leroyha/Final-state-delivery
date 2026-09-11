# Final-State Delivery（最终状态交付）

[English](README.md) | [简体中文](README.zh-CN.md)

[![GitHub Stars](https://img.shields.io/github/stars/Leroyha/Final-state-delivery?style=flat-square)](https://github.com/Leroyha/Final-state-delivery/stargazers)
[![平台](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey?style=flat-square)](#兼容性)
[![协议：MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://opensource.org/licenses/MIT)

## AI 应该交付结果，而不是交付对话历史

Final-State Delivery（最终状态交付）是一套面向 Vibe Coding 和 AI 编程代理的规范与实践资料，用于应对一种常见问题：被否决的想法、被放弃的实现方式或局部纠正，继续泄漏到最终代码、测试、界面、文档、记忆或新的全局规则中。

> **“没有东坡肉的番茄炒蛋”原则**
>
> 当目标是一个简单的菜、功能、页面或文档时，交付目标本身。被丢弃的成分或实现方式不应继续成为产品身份的一部分。

本项目提供简明的 `AGENTS.md` 规范、作用域模型、工具无关的实践建议、案例研究和评估标准，适用于 ChatGPT/Codex、Claude Code、Gemini CLI、GitHub Copilot、Grok Build、Cursor 以及其他 AI 编程代理。

## 问题概述

在普通工程流程中，产品记录当前支持的行为和真正需要长期保留的约束。在 AI 辅助开发流程中，模型可以看到大量完整对话，并可能把其中每个醒目的陈述都当作候选指令。因此，一次局部纠正可能继续出现在：

- 描述被删除内容而不是当前结果的 PR 标题；
- 为被放弃方案保留的注释、测试或验证器；
- 向用户展示不存在功能的界面或文档文案；
- 把任务级决定变成用户偏好的记忆；
- 只为防止一次误解再次发生而增加的大量代码。

本项目将这种现象称为 **Rejected-Context Leakage（被否决上下文泄漏）**：本应随任务结束而失效的对话材料，被带入最终交付物或后续无关任务。

## 核心规范

完整规范位于 [`AGENTS.md`](AGENTS.md)，可复制版本位于 [`templates/AGENTS.md`](templates/AGENTS.md)。

```text
Treat corrections as updates to the current task, not as lasting user preferences or project requirements.
Deliver the intended final state. Do not preserve rejected ideas, intermediate attempts, correction history, or conversational residue in code, UI text, comments, tests, documentation, commits, or PR descriptions.
Describe what the resulting system does. Include historical context only when it is necessary to understand a non-obvious constraint, compatibility requirement, migration, or safety decision.
Keep changes proportional to the request. Removing or simplifying behavior should normally reduce or preserve complexity unless the final requirements independently justify additional code.
Add tests for supported behavior and credible regressions. Do not create permanent guards solely for an abandoned implementation or a one-time misunderstanding.
Apply constraints only within their demonstrated scope. Do not infer general preferences, unrelated restrictions, or future requirements from a local correction.
Persist a rule or preference only when the user explicitly requests persistence or when it is already an established project requirement.
Before finishing, review the diff as a clean final implementation: relevant, minimal, internally consistent, and free of unnecessary process narration.
```

## 为什么采用短规范

这套规范建立四条边界：

1. **最终状态：** 描述修改完成后实际存在的内容。
2. **任务作用域：** 纠正只作用于被证明需要它的组件、功能或任务。
3. **生命周期：** 临时对话状态随任务结束，除非用户明确要求持久化。
4. **比例原则：** 实现复杂度应与支持的结果和真实风险相匹配。

规范不使用某个具体食物、功能、模型或事故作为全局禁令，从而降低案例本身再次成为污染源的风险。

## 快速使用

1. 将 [`AGENTS.md`](AGENTS.md) 或较短的 [`templates/AGENTS.md`](templates/AGENTS.md) 放入使用 AI 编程代理的项目。
2. 用 [`templates/task-spec.md`](templates/task-spec.md) 写明当前任务的目标、范围、验收标准和持久化决定。
3. 要求代理实现当前支持的行为，并检查最终 diff。
4. 从相关性、最小性、历史残留和作用域扩张四个方面审查最终结果。

## 文档导航

| 文档 | 内容 |
| --- | --- |
| [`docs/problem-statement.zh-CN.md`](docs/problem-statement.zh-CN.md) | 问题定义和可观察表现 |
| [`docs/llm-analysis.zh-CN.md`](docs/llm-analysis.zh-CN.md) | LLM 与上下文机制分析 |
| [`docs/vibe-coding-analysis.zh-CN.md`](docs/vibe-coding-analysis.zh-CN.md) | Vibe Coding 工作流分析 |
| [`docs/anti-patterns.zh-CN.md`](docs/anti-patterns.zh-CN.md) | 常见反模式和合理修复方式 |
| [`docs/best-practices.zh-CN.md`](docs/best-practices.zh-CN.md) | 使用和审查建议 |
| [`docs/agent-adapters.zh-CN.md`](docs/agent-adapters.zh-CN.md) | 常见 AI 编程工具适配 |
| [`docs/evaluation.zh-CN.md`](docs/evaluation.zh-CN.md) | 评估场景和验收标准 |
| [`docs/examples/`](docs/examples/) | 具体案例 |
| [`case-materials/provided-discussion.zh-CN.md`](case-materials/provided-discussion.zh-CN.md) | 帖子与评论材料综合 |
| [`templates/`](templates/) | 可复制模板 |

## 项目声明

本项目是一套行为规范和工作流干预方案。它可以通过澄清状态、作用域、持久化和最终 diff 审查来降低上下文残留风险，但不能保证任何模型永远不会重复醒目词语、推断未声明偏好或生成不成比例的改动。

## 兼容性

文档适用于 macOS、Windows 和 Linux 上的 AI 编程流程，也适用于 ChatGPT/Codex、Claude Code、Gemini CLI、GitHub Copilot、Grok Build、Cursor 等工具。

## 搜索关键词

本 README 有意包含以下中英文搜索概念：`番茄炒蛋不要东坡肉`、番茄炒蛋（无东坡肉）、`Tomato Egg Without Dongpo Pork`、`Final-State Delivery`、`rejected-context leakage`、`conversation residue` 和 `AI coding agent scope creep`。

## Star 趋势

[![Star History Chart](https://api.star-history.com/svg?repos=Leroyha/Final-state-delivery&type=Date)](https://star-history.com/#Leroyha/Final-state-delivery&Date)

案例材料应注明来源，必要时采用改写或摘要，并与规范文件分离。GitHub 建仓时选择 MIT License。
