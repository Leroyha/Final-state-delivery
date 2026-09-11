# Project Structure

[English](project-structure.md) | [简体中文](project-structure.zh-CN.md)

```text
final-state-delivery/
├── AGENTS.md                         # Canonical repository delivery rule
├── README.md                         # English entry point and discoverability text
├── README.zh-CN.md                   # Chinese entry point and discoverability text
├── .gitignore                        # Local-only and generated-file exclusions
├── case-materials/
│   ├── README.md                      # English attribution and privacy policy
│   ├── README.zh-CN.md                # Chinese attribution and privacy policy
│   ├── provided-discussion.md         # English synthesis of the supplied discussion
│   └── provided-discussion.zh-CN.md   # Chinese synthesis and source link
├── docs/
│   ├── README.md / README.zh-CN.md     # Documentation navigation
│   ├── project-structure.md            # English file map
│   ├── project-structure.zh-CN.md      # Chinese file map
│   ├── problem-statement.md            # Definition and observable failure patterns
│   ├── problem-statement.zh-CN.md      # Chinese problem definition
│   ├── llm-analysis.md / .zh-CN.md     # LLM and context analysis
│   ├── vibe-coding-analysis.md / .zh-CN.md # Workflow analysis
│   ├── anti-patterns.md / .zh-CN.md    # Failure patterns and responses
│   ├── best-practices.md / .zh-CN.md   # Operational guidance
│   ├── agent-adapters.md / .zh-CN.md   # Tool-neutral adapter guidance
│   ├── evaluation.md / .zh-CN.md      # Scenarios and acceptance rubric
│   ├── references.md / .zh-CN.md      # Background sources
│   └── examples/
│       ├── tomato-egg.md / .zh-CN.md   # Central public case analogy
│       ├── feature-removal.md / .zh-CN.md # Removal example
│       └── scope-boundary.md / .zh-CN.md # Scope example
└── templates/
    ├── AGENTS.md                       # Minimal English copyable rule
    ├── AGENTS.zh-CN.md                 # Chinese explanation of the rule
    ├── task-spec.md / .zh-CN.md        # Task and acceptance template
    └── pr-template.md / .zh-CN.md      # Final-state PR template
```

## Ownership rules

- `AGENTS.md` and `templates/AGENTS.md` are the normative rule sources.
- `README.md` and `README.zh-CN.md` are the bilingual project entry points.
- `docs/` contains problem analysis, cases, tool guidance, evaluation, and references.
- `case-materials/` contains source material and does not silently become normative.
- `templates/` contains reusable artifacts for other AI coding projects.

When adding a new document, place it under the narrowest applicable directory and add it to `docs/README.md` or this map. Keep the normative rule short; put explanations in the explanatory documents.
