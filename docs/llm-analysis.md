# LLM and Context Analysis

[English](llm-analysis.md) | [简体中文](llm-analysis.zh-CN.md)

This document explains why rejected-context leakage is plausible in current language-model workflows. It intentionally uses qualified language. A model's output is the result of many interacting factors, and the mechanisms below should not be read as a single proven cause for every incident.

## 1. A negative instruction still activates its subject

To interpret a sentence such as "do not include X", a model must represent the instruction and the referenced concept. The text of the concept remains in the prompt even when the intended action is omission. This creates a practical salience problem: repeating a rejected concept gives it more textual presence and more opportunities for completion around it.

This is related to, but not identical with, the popular "do not think of an elephant" effect. Human cognitive findings do not automatically transfer to neural language models. The defensible engineering conclusion is narrower: repeated negative wording is still context, and context selection is a central part of model behavior. Positive descriptions of the desired final state usually provide a cleaner target.

## 2. Instruction following rewards visible evidence of understanding

Instruction-tuned models are optimized to produce responses that humans judge useful, relevant, and compliant. In a chat setting, a short acknowledgement can be helpful. In a coding workflow, the same tendency can become over-confirmation: the model restates the correction in a plan, a comment, a test name, a PR description, and a memory entry.

This is not a conscious motive. It is a generation pattern shaped by the prompt, demonstrations, reward signals, and the local conversation. The practical boundary is simple: acknowledgement belongs in the working exchange; the repository should retain only information needed to operate and maintain the resulting system.

## 3. The context window is not a requirements database

A long conversation contains requirements, examples, hypotheses, rejected proposals, emotional emphasis, tool output, and transient debugging state. Unless an external system labels and filters these categories, they are all presented as model context. More context can improve recall, but it can also dilute priority and make an old statement available at the wrong time.

Research on long-context models has shown that information position and retrieval conditions affect performance. This supports a workflow rule: provide the current task and its acceptance criteria in a compact, authoritative form, and avoid asking the model to treat the entire conversation as a permanent specification.

## 4. Correction history can be mistaken for a durable requirement

The phrase "remove this from the current page" has a different lifecycle from "never use this in any future project". Natural language often leaves that lifecycle implicit. An agent that optimizes for helpfulness may infer a broader rule, especially when a memory tool or repository instruction file is available.

The error is a scope transition:

```text
local correction -> task requirement -> repository rule -> user preference
```

Final-State Delivery makes the transition explicit. Persistence is opt-in unless a project rule already establishes it.

## 5. Rejected ideas create a completion attractor

When the conversation repeatedly contrasts an intended result with a rejected alternative, the model receives many opportunities to continue that contrast. A response can therefore preserve the structure of the debate even after the debate is over. This explains why a final answer may contain a long explanation of an absent feature even when the implementation is technically correct.

The remedy is not a larger blacklist of words. It is a final-state representation with positive acceptance criteria, followed by a diff review that treats unnecessary residue as a defect.

## 6. Compensatory complexity is not the same as robust engineering

A model may add safeguards after a correction because extra structure appears to demonstrate reliability. Such structure is justified only when it protects supported behavior or a credible recurring risk. A one-time misunderstanding does not automatically warrant a detector, deny-list, validator, or permanent regression suite.

The engineering test is:

> If the historical conversation were unavailable, would this code still be justified by the current product contract, a security requirement, a compatibility requirement, or a credible regression?

If the answer is no, the change deserves removal or simplification.

## 7. Memory systems amplify lifecycle mistakes

External memory changes the risk profile. A model may use a memory file, project rule, IDE instruction, or retrieval index on a later task. A mistaken memory entry has a longer lifetime than a chat turn and can influence unrelated work.

Memory should therefore store stable, user-authorized preferences and project facts. It should not become an incident log or a list of words associated with a past correction. A memory write is a state-changing operation and should be evaluated with the same scope discipline as a code change.

## 8. What the evidence supports

The combined literature and engineering experience support these modest conclusions:

- prompt content, ordering, and repetition affect generation;
- instruction tuning encourages models to follow and often explain instructions;
- long-context retrieval is imperfect and position-sensitive;
- external memory can carry stale information across tasks;
- human review remains necessary for scope, proportionality, and final-state quality.

They do not support a universal claim that every negative instruction increases a concept's internal attention weight, or that one short rule can fully control every model and tool. The specification should remain useful under that uncertainty.

## 9. Design implications

The practical controls are therefore:

1. State the desired outcome positively and concretely.
2. Mark task-local constraints with an explicit scope and lifetime.
3. Keep rejected approaches out of durable artifacts.
4. Review the final diff and user-facing text as a clean system snapshot.
5. Persist memory only with explicit authorization or an existing project rule.
6. Prefer supported-behavior tests over tests for abandoned history.

See [`references.md`](references.md) for the source material behind these claims.
