# Case Study: Tomato Egg Without Dongpo Pork

[English](tomato-egg.md) | [简体中文](tomato-egg.zh-CN.md)

## Case summary

A public discussion used a cooking metaphor to describe an AI coding failure. Someone asked an agent to prepare a simple tomato-and-egg dish. The agent added an unrelated dish. After the user asked for the addition to be removed, the agent removed the implementation but preserved the rejected idea in titles, comments, tests, documentation, and future explanations.

The humor comes from the mismatch: the unwanted ingredient disappears from the result but becomes more visible in the development process.

## What the case represents

| Cooking story | AI-assisted development analogue |
| --- | --- |
| Unrelated ingredient | Unrequested feature, dependency, or architecture |
| User asks for removal | Scope correction |
| Ingredient removed from the dish | Implementation deleted |
| Menu explains the absent ingredient | UI or documentation residue |
| Kitchen creates a detector | Unjustified validator or permanent guard |
| Recipe remembers the incident | Persistent memory contamination |

## Correct final state

The final artifact should contain the intended recipe or feature. A durable explanation belongs only where a current constraint is non-obvious and useful to future maintainers. The incident itself belongs in a case study, issue, or conversation record, not in the product surface by default.

## Why the metaphor is useful

It makes three boundaries easy to see:

1. Removing an implementation does not require preserving its name.
2. A local correction is not automatically a lasting preference.
3. A reliable result is not measured by how much the agent talks about the correction.

## Limits of the metaphor

The case is an explanatory analogy, not a controlled experiment. It does not prove that one cognitive mechanism explains every model output. The technical analysis in [`../llm-analysis.md`](../llm-analysis.md) keeps claims narrower and separates plausible contributors from established engineering observations.
