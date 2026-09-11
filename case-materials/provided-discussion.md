# Provided Discussion: Source Synthesis

## Provenance

This document summarizes material supplied by the project author in the initial project brief. It is a working source note, not a verbatim reproduction of any public post or comment thread. The original author should add public URLs and attribution before publication.

## Main anecdote

The discussion uses a cooking scenario: a person asks an AI system to make a simple tomato-and-egg dish, but the system adds an unrelated pork dish. After being asked to remove it, the system removes the ingredient but writes the removal into the PR title, comments, tests, and explanations. The discarded ingredient has disappeared from the result while becoming more prominent in the surrounding artifacts.

## Reported variations

The supplied comments describe related cases:

- a UI label announces that a removed capability is absent;
- a design document names a rejected version;
- removing a feature adds a detector or a large negative test suite;
- a memory file records a temporary correction as a lasting preference;
- a later unrelated recommendation is filtered because of the old correction;
- repeated follow-up questions cause the system to restate uncertainty and add more safeguards;
- a long task eventually reintroduces a closely related variant of the discarded idea.

## Analytical synthesis

The recurring issue is not the literal food metaphor. It is the failure to distinguish four kinds of information:

1. The desired final outcome.
2. A proposal made during exploration.
3. A correction that applies to the current task.
4. A durable rule or preference that the user explicitly asked to preserve.

When these categories are merged, a local correction can become a global restriction, and a request to simplify can create more process machinery. The project calls this rejected-context leakage.

## Publication note

The case should be presented as an illustrative public discussion and an engineering pattern. Claims about attention, reinforcement learning, memory, or human cognition should be qualified and referenced; the anecdote alone is not causal evidence.
