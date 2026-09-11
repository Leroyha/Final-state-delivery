# Applying the Rule Across Agent Tools

Final-State Delivery is tool-neutral. The exact file name, instruction hierarchy, memory feature, and review workflow vary by product and version. Check the current tool documentation before relying on a vendor-specific behavior.

## Repository instruction files

When a tool supports repository instruction files, place the concise rule at the repository root and keep project-specific architecture below it. A local instruction file may refine scope for a subdirectory, but it should not silently turn a task correction into a user-wide preference.

## ChatGPT and Codex

Use the repository `AGENTS.md` as the durable project rule and put the current request in the task message or task specification. When the agent asks for clarification, answer the acceptance question rather than expanding a past correction into a general preference. Review the diff and final response together.

## Claude Code

Use the repository instruction mechanism supported by the current Claude Code release. Keep the canonical rule short and let project-specific files describe architecture, commands, and tests. When a task changes direction, update the current task contract and ask for a clean final diff review.

## Gemini CLI

Use the repository guidance mechanism supported by the installed version. Keep durable project facts separate from the exploratory prompt. If a local memory or context file is used, apply the same persistence rule: store stable, authorized preferences and project facts only.

## GitHub Copilot

Place the rule in the repository instruction location supported by the current Copilot experience, and keep the same wording across repository and IDE integrations where practical. PR descriptions should be generated from the final diff and acceptance criteria, not copied from the entire chat.

## Cursor and similar IDE agents

Keep the global instruction layer general and the project layer concrete. A project rule should explain the current codebase and delivery standard; it should not contain a catalogue of historical mistakes. Use the final diff as the authority for what changed.

## A portable prompt wrapper

For tools without repository instruction support, include this compact request around a task:

```text
Implement the current task according to its stated acceptance criteria. Treat corrections as local updates to this task unless persistence is explicitly requested. Deliver a clean final state: retain only code, tests, documentation, and rationale needed for the supported behavior or a credible requirement. Review the final diff for irrelevant history, scope expansion, and unjustified complexity.
```

## Compatibility limits

No instruction file can override higher-priority safety or platform policies, and no wording can guarantee deterministic model behavior. The rule improves the specification and review boundary; it does not remove the need for human acceptance.
