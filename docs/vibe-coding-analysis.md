# Vibe Coding and the Final-State Boundary

[English](vibe-coding-analysis.md) | [简体中文](vibe-coding-analysis.zh-CN.md)

## What changes when an agent writes the code

Vibe Coding is an AI-assisted development style in which a person describes an outcome and an agent explores, edits, tests, and explains the implementation. The person remains responsible for the product intent and acceptance boundary, while the agent can perform much of the mechanical work.

This changes the shape of failure. In a manual workflow, a rejected design usually disappears from the working tree unless someone deliberately records it. In an agent workflow, the rejected design remains in the conversation that controls the next action. The same context can then influence source code, tests, documentation, and release text.

## The agent loop

```text
🟦 Request -> 🟩 Plan -> 🟨 Inspect -> 🟧 Implement -> 🟪 Test -> 🟫 Explain -> 🔄 Revise
                                                     ^                         |
                                                     +----- Back to inspect ---+
```

The loop is productive when each cycle narrows the implementation toward the current contract. It becomes noisy when explanations of earlier cycles are treated as requirements for later cycles.

## Four boundaries for a healthy workflow

### Product boundary

The repository and application should expose supported behavior, durable constraints, and necessary rationale. They should not expose discarded proposals merely because they appeared during development.

### Task boundary

The current request owns its acceptance criteria. A correction to one task should not silently rewrite unrelated tasks, future recommendations, or the user's general profile.

### Memory boundary

Long-lived memory should contain stable facts and explicitly requested preferences. A temporary correction, failed hypothesis, or rejected implementation belongs to the working context and expires with it.

### Review boundary

The final diff, test result, rendered UI, and user-facing text are the evidence of completion. A confident explanation is not evidence that the implementation is scoped correctly.

## A practical Vibe Coding workflow

### 1. Write a positive task contract

State the desired behavior, affected paths, acceptance criteria, and required constraints. Use [`../templates/task-spec.md`](../templates/task-spec.md). Keep the contract shorter and more authoritative than the exploratory conversation.

### 2. Separate exploration from delivery

Allow the agent to consider alternatives during planning, but make the delivery target explicit before implementation. The final task specification should contain selected requirements, not every discarded possibility.

### 3. Ask for proportional changes

The agent should first inspect the current implementation and then make the smallest coherent change that satisfies the contract. A removal or simplification should not acquire a large defensive subsystem without an independent reason.

### 4. Validate behavior and scope

Run the project's normal checks. Then inspect the diff for residual plan language, unnecessary guards, unrelated file changes, and new persistent preferences. This second review is part of acceptance, not optional polish.

### 5. Close the task cleanly

The final handoff should summarize the resulting behavior, files changed, tests run, and any real limitation. It should not reproduce the conversation or advertise discarded approaches.

## What this project does not recommend

It does not recommend hiding safety rationale, removing legitimate regression coverage, or banning all explanation. Non-obvious security, compatibility, migration, legal, and operational constraints belong in durable documentation when future maintainers need them. The requirement is relevance and scope, not silence.
