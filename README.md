# Final-State Delivery

[English](README.md) | [简体中文](README.zh-CN.md)

[![GitHub stars](https://img.shields.io/github/stars/Leroyha/Final-state-delivery?style=flat-square)](https://github.com/Leroyha/Final-state-delivery/stargazers)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey?style=flat-square)](#compatibility)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://opensource.org/licenses/MIT)

## AI agents should deliver the result, not the history of the conversation

Final-State Delivery is a concise specification and practical documentation set for AI coding agents used in Vibe Coding workflows. It addresses a recurring failure mode: a rejected idea, abandoned implementation, or local correction leaks into the final codebase as commentary, tests, UI text, memory, or a new global rule.

> **The Tomato Egg Without Dongpo Pork Principle**
>
> When the intended result is a simple dish, feature, page, or document, deliver that result. Do not turn the discarded ingredient or discarded implementation into a permanent part of the product's identity.

This repository gives teams a compact `AGENTS.md` rule, a scope model, a set of tool-neutral practices, case studies, and an evaluation rubric. It is designed for ChatGPT/Codex, Claude Code, Gemini CLI, GitHub Copilot, Grok Build, Cursor, and other instruction-following coding agents.

## The problem in one minute

In an ordinary engineering workflow, the product records the supported behavior and the rationale for durable constraints. In an AI-assisted workflow, the model sees the entire working conversation and may treat every salient statement as a candidate instruction. A local correction can therefore reappear as:

- a PR title that describes what was removed instead of what now exists;
- comments, tests, or validators for an abandoned approach;
- UI or documentation text that advertises an absent feature;
- a memory entry that turns a task-local decision into a user preference;
- additional code whose only purpose is to defend against a one-time misunderstanding.

The underlying issue is **rejected-context leakage**: conversational material that should have expired is carried into the final artifact or a later, unrelated task.

## The canonical rule

The complete repository rule is in [`AGENTS.md`](AGENTS.md). The reusable template is in [`templates/AGENTS.md`](templates/AGENTS.md).

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

## Why this wording is deliberately short

The rule defines four durable boundaries:

1. **Final state:** describe what exists now.
2. **Task scope:** keep a correction within the component, feature, or task where it was demonstrated.
3. **Lifecycle:** let temporary conversation state expire unless persistence is explicitly requested.
4. **Proportionality:** make the implementation no more complex than the supported outcome requires.

It does not name a particular food, feature, vendor, model, or incident. This keeps the rule reusable and reduces the chance that the example itself becomes the next global preference.

## Quick start

1. Copy [`AGENTS.md`](AGENTS.md), or the shorter [`templates/AGENTS.md`](templates/AGENTS.md), into a repository that uses AI coding agents.
2. Put the current task's positive outcome, scope, acceptance criteria, and required constraints in a task specification. Use [`templates/task-spec.md`](templates/task-spec.md).
3. Ask the agent to implement the supported behavior and verify the final diff.
4. Review the final artifact for relevance, minimality, residual conversation history, and scope expansion.

The specification is compatible with repository instruction files, but it does not replace project-specific architecture, security, testing, or release requirements.

## Documentation map

| Document | Purpose |
| --- | --- |
| [`docs/problem-statement.md`](docs/problem-statement.md) | Defines the failure mode and its observable patterns. |
| [`docs/llm-analysis.md`](docs/llm-analysis.md) | Gives a careful, qualified analysis of model and context mechanisms. |
| [`docs/vibe-coding-analysis.md`](docs/vibe-coding-analysis.md) | Connects the problem to AI-assisted development workflows. |
| [`docs/anti-patterns.md`](docs/anti-patterns.md) | Shows recurring failure patterns and proportionate corrections. |
| [`docs/best-practices.md`](docs/best-practices.md) | Provides operational guidance for users and agent maintainers. |
| [`docs/agent-adapters.md`](docs/agent-adapters.md) | Explains how to apply the rule across common coding tools. |
| [`docs/evaluation.md`](docs/evaluation.md) | Provides scenarios and a review rubric for measuring outcomes. |
| [`docs/examples/`](docs/examples/) | Contains concrete, tool-neutral examples. |

## What this project claims

This is a behavioral specification and a workflow intervention. It can reduce residual-context failures by clarifying state, scope, persistence, and final-diff review. It cannot guarantee that a model will never repeat a salient term, infer an unstated preference, or make a disproportionate change. Model behavior depends on the model, context window, instruction hierarchy, memory features, tools, and human review.

The project therefore treats the final diff and supported behavior as the acceptance boundary. It does not claim that a single prompt can solve all context-management problems.

## Compatibility

The documentation applies to AI coding workflows on macOS, Windows, and Linux. The guidance is tool-neutral and can be used with ChatGPT/Codex, Claude Code, Gemini CLI, GitHub Copilot, Grok Build, Cursor, and similar agents.

## Search and discoverability

The Chinese and English search concepts intentionally appear in this README: `番茄炒蛋不要东坡肉`, `番茄炒蛋（无东坡肉）`, `Tomato Egg Without Dongpo Pork`, `Tomato Egg (Without Dongpo Pork)`, `Final-State Delivery`, `rejected-context leakage`, `conversation residue`, and `AI coding agent scope creep`.

Case material should be attributed, paraphrased when necessary, and kept separate from the normative template. Select the MIT license when creating the GitHub repository.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Leroyha/Final-state-delivery&type=Date)](https://star-history.com/#Leroyha/Final-state-delivery&Date)
