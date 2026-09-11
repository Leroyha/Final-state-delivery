# Anti-Patterns

These patterns describe common outcomes, not rules for a particular repository. The examples use generic feature names so that the case itself does not become a new project-wide restriction.

## 1. Removal inflation

**Symptom:** A small removal produces a large validator, detector, deny-list, or collection of tests.

**Why it is harmful:** The diff protects an abandoned history instead of a supported contract. It increases maintenance cost and can make a legitimate future change harder.

**Proportionate response:** Remove the unsupported implementation. Keep or add tests only for behavior that remains supported or for a demonstrated recurring regression.

## 2. Conversation-shaped PR text

**Symptom:** The PR title and body narrate the agent's earlier mistake, the user's correction, and the discarded options.

**Why it is harmful:** Reviewers must reconstruct the actual result from process narration. The repository history becomes coupled to a transient conversation.

**Proportionate response:** Describe the final behavior, user-visible impact, relevant files, validation, and any durable tradeoff.

## 3. Absence announcement

**Symptom:** A UI, help page, or public document tells users that a removed capability is absent.

**Why it is harmful:** The product surface advertises implementation history and creates a question users did not have.

**Proportionate response:** Remove the obsolete surface. Document a supported limitation only when it affects user decisions or operations.

## 4. Historical comment residue

**Symptom:** A comment explains a proposal that was considered and rejected, even though the current code no longer needs that explanation.

**Why it is harmful:** Future maintainers may treat the abandoned rationale as a current constraint.

**Proportionate response:** Keep comments for non-obvious current constraints. Delete comments whose only purpose is to narrate a completed correction.

## 5. Local correction as global preference

**Symptom:** A decision about one output or component is written into global memory or used to filter unrelated future work.

**Why it is harmful:** The model's context becomes less relevant and the user loses control over future choices.

**Proportionate response:** Keep the decision task-local unless the user explicitly asks for persistence or an existing project rule requires it.

## 6. Reverse testing

**Symptom:** Tests primarily assert that an abandoned idea never appears, rather than asserting the behavior the product is supposed to support.

**Why it is harmful:** The test suite encodes history and may block valid future requirements without protecting a product contract.

**Proportionate response:** Test supported behavior, credible regressions, security boundaries, and compatibility contracts.

## 7. Permanent disclaimer language

**Symptom:** Documentation is filled with statements about what the project does not do, even though those absences are not user-relevant constraints.

**Why it is harmful:** Negative lists become a second, noisy specification and can make the rejected concept more discoverable than the feature itself.

**Proportionate response:** Describe the intended capability and document meaningful boundaries only where they help users or maintainers make a decision.

## 8. Corrective recursion

**Symptom:** The agent adds a rule to prevent a previous rule from recurring, then adds another rule to protect the rule, creating a self-referential instruction stack.

**Why it is harmful:** The instruction hierarchy becomes harder to interpret and the original product task disappears under process controls.

**Proportionate response:** Retain one concise durable principle and rely on task scope plus final-diff review.
