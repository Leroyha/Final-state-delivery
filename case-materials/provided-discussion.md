# Provided Discussion: Source Synthesis

[English](provided-discussion.md) | [简体中文](provided-discussion.zh-CN.md)

## Provenance

This document summarizes material supplied by the project author in the initial project brief. It is a working source note, not a verbatim reproduction of any public post or comment thread. The original author should add public URLs and attribution before publication.

## Main anecdote

The discussion uses a cooking scenario: a person asks an AI system to make a simple tomato-and-egg dish, but the system adds an unrelated pork dish. After being asked to remove it, the system removes the ingredient but writes the removal into the PR title, comments, tests, and explanations. The discarded ingredient has disappeared from the result while becoming more prominent in the surrounding artifacts.

## Source post

Original post: https://x.com/songkeys/status/2090416137720999992

The source author, source text, and interaction data should be verified on the original post page. The live post may change over time.

## Representative original text

The following is an English translation of the original post text:

> What I cannot stand most about GPT-5.6 is this: I ask it to make a plate of tomato and eggs, and it adds Dongpo pork. I ask whether Dongpo pork is necessary. It says I am right and removes the Dongpo pork. I say, fine, open a PR. Then I see that the PR is titled “tomato and eggs (without Dongpo pork),” and the comments contain a long explanation of why this dish does not need Dongpo pork.

The translated quote is included to make the case understandable to English readers. The source language and source link should remain the authority for attribution.

## Reported variations

The project author supplied additional comment material describing related cases. The following is a synthesis of that material:

- a UI label announces that a removed capability is absent;
- a design document names a rejected version;
- removing a feature adds a detector or a large negative test suite;
- a memory file records a temporary correction as a lasting preference;
- a later unrelated recommendation is filtered because of the old correction;
- repeated follow-up questions cause the system to restate uncertainty and add more safeguards;
- a long task eventually reintroduces a closely related variant of the discarded idea.

## Representative comment material

The following points are paraphrased from the additional comment material supplied for this project:

- Removing one feature can make an AI-generated implementation longer instead of shorter.
- A removed feature does not need a detector or a permanent test suite whose only purpose is to keep the old feature away.
- Do not create tests for a grave: tests should protect supported behavior, not memorialize an abandoned implementation.
- The best change should look like the intended system had always been that way.
- A local correction should not be reused as a global preference in an unrelated recommendation or task.

## Analytical synthesis

The recurring issue is not the literal food metaphor. It is the failure to distinguish four kinds of information:

1. The desired final outcome.
2. A proposal made during exploration.
3. A correction that applies to the current task.
4. A durable rule or preference that the user explicitly asked to preserve.

When these categories are merged, a local correction can become a global restriction, and a request to simplify can create more process machinery. The project calls this rejected-context leakage.

## Publication note

The case should be presented as an illustrative public discussion and an engineering pattern. Claims about attention, reinforcement learning, memory, or human cognition should be qualified and referenced; the anecdote alone is not causal evidence.
