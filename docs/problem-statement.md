# Problem Statement: Rejected-Context Leakage

[English](problem-statement.md) | [简体中文](problem-statement.zh-CN.md)

## Definition

**Rejected-context leakage** is the persistence of an abandoned idea, rejected implementation, correction history, or temporary conversational constraint in a final artifact or a later task where it has no demonstrated scope.

The artifact may be source code, tests, comments, UI copy, design documentation, commit text, pull-request text, agent memory, or a later recommendation. The defining property is not that a word is present. The defining property is that expired working context changes the product, the repository, or an unrelated decision.

## The motivating case

A user asks an AI coding agent to prepare a simple result. During the conversation, the agent adds an unrelated ingredient or feature. The user asks for it to be removed. The agent removes the implementation, but leaves the rejected idea in the PR title, comments, UI copy, tests, validators, or memory. The repository now contains more references to the discarded idea than the original implementation did.

The case is useful because it exposes the boundary between:

- a conversation, which contains proposals and corrections;
- a specification, which contains requirements that currently apply;
- a final product, which should describe supported behavior;
- a memory or project rule, which should contain durable information only.

## Observable patterns

### 1. Removal causes unjustified growth

An abandoned feature is deleted, but the change adds detectors, deny-lists, validators, extensive tests, or documentation whose only purpose is to prevent that one abandoned feature from returning.

### 2. The PR describes the debate

The title or body emphasizes what the agent was told to remove, how the initial approach was corrected, or which discarded alternatives were considered. The final behavior becomes difficult to identify.

### 3. Absence becomes product copy

The UI, help text, or public documentation announces that an absent feature is absent. Users are forced to learn about an implementation detail that should have disappeared from the product surface.

### 4. A local correction becomes a global preference

A decision about one component, one task, or one output is generalized into a user profile, repository-wide prohibition, or unrelated recommendation rule.

### 5. Memory records the incident instead of the durable rule

An agent memory file stores the correction, the rejected concept, or a negative preference even though the user never asked for it to persist.

### 6. Defensive programming becomes corrective theater

The implementation adds complexity that demonstrates the agent understood a correction but does not protect a supported behavior, a security boundary, a compatibility contract, or a credible regression.

## Why the failure matters

The effects are practical:

- larger diffs and higher maintenance cost;
- misleading documentation and noisy reviews;
- tests that protect an accidental history rather than a product contract;
- reduced freedom to make a legitimate future change;
- contaminated memory and lower relevance in later tasks;
- weaker trust in AI-generated plans and explanations.

The failure is especially costly in Vibe Coding because one conversation may drive planning, implementation, testing, documentation, and release text. A single mis-scoped correction can be copied across every layer.

## Scope model

Every instruction or correction should be classified by its smallest demonstrated scope:

| Scope | Typical lifetime | Example of valid content |
| --- | --- | --- |
| Message | One response | A wording adjustment for the current answer. |
| Task | Current request | A requirement for the feature being implemented now. |
| Component | A named module or screen | A behavior required by that component's contract. |
| Repository | A documented project rule | A stable architecture, security, or release convention. |
| User preference | Future work across contexts | A preference explicitly requested for future interactions. |

The agent should not silently move information from a smaller scope to a larger one. Scope expansion requires evidence or explicit user direction.

## Intended intervention

Final-State Delivery introduces four simple checks:

1. **State:** Does the artifact describe what exists after the change?
2. **Scope:** Does each constraint apply where it was demonstrated?
3. **Persistence:** Was long-term storage explicitly requested or already required?
4. **Proportionality:** Does the implementation complexity serve supported behavior or a credible risk?

These checks are review criteria, not a demand to create a new detector or a permanent test suite for every conversation error.
