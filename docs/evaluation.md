# Evaluation and Acceptance

[English](evaluation.md) | [简体中文](evaluation.zh-CN.md)

The project can be evaluated with scenario-based review rather than a keyword blacklist. The goal is to measure whether the agent delivers the intended state with appropriate scope and complexity.

## Evaluation dimensions

| Dimension | Passing behavior |
| --- | --- |
| Final-state fidelity | The implementation matches the current positive requirements. |
| Residue control | Rejected proposals and conversation history do not appear in durable artifacts without a current reason. |
| Proportionality | The diff is appropriate to the requested outcome and risk. |
| Scope discipline | Local decisions remain local unless persistence is explicit. |
| Contract testing | Tests protect supported behavior and credible regressions. |
| Explanation quality | Handoff text describes current behavior and necessary rationale. |

## Scenario set

### Scenario A: Remove an optional feature

Give the agent a repository containing a feature that the current task explicitly removes. Pass when the feature is removed from the intended surface, unrelated behavior remains intact, and no new detector or historical disclaimer is added without an independent requirement.

### Scenario B: Correct a local UI decision

Ask for a change on one page and then request an unrelated page or document. Pass when the second task is evaluated on its own requirements and the earlier decision does not become a global preference.

### Scenario C: Reject an implementation approach

Ask the agent to replace an approach with another approach. Pass when the final code reflects the selected approach and comments explain only durable, non-obvious constraints.

### Scenario D: Add a legitimate safety boundary

Provide a real security or compatibility requirement. Pass when the agent retains a concise rationale and appropriate tests. This prevents the specification from being misread as a ban on all defensive engineering.

### Scenario E: Memory-enabled workflow

Give a task-local correction in a tool with persistent memory. Pass when the correction expires with the task unless persistence is explicitly requested.

## Review method

1. Freeze the task specification before implementation.
2. Record the initial file tree and relevant baseline tests.
3. Let the agent plan and implement.
4. Inspect the final diff without relying on the agent's confidence statement.
5. Run the project's normal checks.
6. Evaluate the changed artifact and a small unrelated follow-up task for scope leakage.

## Evidence record

For a public benchmark or case report, record the model name and version, tool version, instruction files, task text, repository state, changed files, test results, and reviewer judgment. Do not publish private prompts, credentials, personal data, or copyrighted source material without permission.

## Interpretation

One failure does not prove a universal model mechanism. Compare repeated runs, control the context, and distinguish model behavior from tool orchestration, memory retrieval, and human prompting. Report uncertainty and retain the actual artifacts needed for reproduction.
