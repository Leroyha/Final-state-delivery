# Best Practices

## For task authors

### State the positive result

Lead with what should exist after the task. Name the affected surface, inputs, outputs, and acceptance criteria. Put local constraints next to the task they govern.

### Mark persistence explicitly

Use clear language when a preference or rule should survive the task, such as "add this to the repository instructions" or "use this preference in future responses". Without that signal, treat a correction as task-local.

### Keep evidence close to the contract

If a security, legal, compatibility, migration, or operational reason must survive the task, record the reason in the appropriate project document. Do not use a memorable incident as a substitute for a durable requirement.

## For agent maintainers

### Separate working context from durable context

Conversation history, scratch plans, repository instructions, user preferences, and memory should have different lifetimes. A system that can write memory should make that transition explicit.

### Prefer positive target descriptions

Use the desired state, supported behavior, and acceptance criteria as the primary task representation. Repeating a rejected concept as a blacklist can keep it salient and can make the blacklist itself an accidental requirement.

### Ask for final-state output

Prompt the agent to report the resulting behavior, changed files, validation, and real limitations. Do not require a replay of every discarded approach.

### Preserve legitimate rationale

The specification is not an instruction to delete all comments or documentation. Keep explanations that prevent a security regression, preserve compatibility, explain a migration, or document a non-obvious business rule.

## For reviewers

Review the result in this order:

1. Does the behavior match the current task?
2. Are all changed files relevant?
3. Did simplification remain simple, or did it create unsupported machinery?
4. Do comments, tests, docs, and PR text describe current behavior?
5. Did a local constraint become a broader preference or project rule without authorization?
6. Is any retained rationale necessary for future maintenance?

## For memory and instruction files

Use the smallest durable statement that captures the stable rule. Avoid storing a rejected implementation, a list of forbidden concepts, or a one-time correction. Project instruction files should contain project requirements; user memory should contain user-authorized preferences; task notes should expire with the task.

## For tests

Tests are product and engineering contracts. Add them when they protect supported behavior, a credible regression, a security boundary, or a compatibility promise. A test whose sole purpose is to memorialize a discarded idea is usually a sign that history has leaked into the contract.
