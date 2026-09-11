# Final-State Delivery

This repository uses the following delivery rule for AI coding agents and human contributors.

- Treat corrections as updates to the current task, not as lasting user preferences or project requirements.
- Deliver the intended final state. Do not preserve rejected ideas, intermediate attempts, correction history, or conversational residue in code, UI text, comments, tests, documentation, commits, or PR descriptions.
- Describe what the resulting system does. Include historical context only when it is necessary to understand a non-obvious constraint, compatibility requirement, migration, or safety decision.
- Keep changes proportional to the request. Removing or simplifying behavior should normally reduce or preserve complexity unless the final requirements independently justify additional code.
- Add tests for supported behavior and credible regressions. Do not create permanent guards solely for an abandoned implementation or a one-time misunderstanding.
- Apply constraints only within their demonstrated scope. Do not infer general preferences, unrelated restrictions, or future requirements from a local correction.
- Persist a rule or preference only when the user explicitly requests persistence or when it is already an established project requirement.
- Before finishing, review the diff as a clean final implementation: relevant, minimal, internally consistent, and free of unnecessary process narration.
