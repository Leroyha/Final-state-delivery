# 在不同 Agent 工具中应用规范

[English](agent-adapters.md) | [简体中文](agent-adapters.zh-CN.md)

Final-State Delivery 与具体工具无关。不同产品和版本的指令层级、文件名、记忆功能和审查流程可能不同，使用前应核对当前工具文档。

## 仓库指令文件

支持仓库指令文件的工具，可以在根目录放置简明规范，把架构、命令和测试等项目要求放在更具体的项目文档中。局部指令可以细化子目录作用域，但不应悄悄把任务纠正变成用户级偏好。

## ChatGPT 与 Codex

将仓库 `AGENTS.md` 作为长期项目规则，把当前请求写入任务消息或任务规格。Agent 需要澄清时，回答验收问题，不要把历史纠正扩大成一般偏好。把 diff 和最终交接内容一起审查。

## Claude Code

使用当前 Claude Code 版本支持的仓库指令机制。保持规范简短，让项目文件描述架构、命令和测试。任务方向改变时，更新当前任务契约，并要求重新检查干净的最终 diff。

## Gemini CLI

使用已安装版本支持的仓库指导机制。把稳定项目事实与探索性提示分开。如果使用本地记忆或上下文文件，同样只保存稳定、已授权的偏好和项目事实。

## GitHub Copilot

将规范放入当前 Copilot 支持的仓库指令位置，并尽量让仓库与 IDE 集成使用相同表述。PR 描述应根据最终 diff 和验收标准生成，不应直接复制整段聊天。

## Grok Build

使用当前 Grok Build 工作流支持的仓库指令机制。让最终任务契约靠近代码库，默认把纠正限制在当前任务，并在交付前检查生成文件和持久化上下文中是否存在不必要的历史残留。

## Cursor 和类似 IDE Agent

保持全局指令通用、项目指令具体。项目规则应解释当前代码库和交付标准，不应列出历史错误目录。最终 diff 是判断修改内容的依据。

## 便携式提示包装

对于不支持仓库指令的工具，可以把下面的短提示放在任务外层：

```text
Implement the current task according to its stated acceptance criteria. Treat corrections as local updates to this task unless persistence is explicitly requested. Deliver a clean final state: retain only code, tests, documentation, and rationale needed for the supported behavior or a credible requirement. Review the final diff for irrelevant history, scope expansion, and unjustified complexity.
```

## 兼容性限制

指令文件不能覆盖更高优先级的安全或平台策略，任何措辞也不能保证模型行为完全确定。规范改善的是规格和审查边界，不能取代人工验收。
