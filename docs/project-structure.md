# Project Structure

```text
final-state-delivery/
├── AGENTS.md                         # Canonical repository delivery rule
├── README.md                         # Bilingual entry point and discoverability text
├── .gitignore                        # Local-only and generated-file exclusions
├── case-materials/
│   ├── README.md                      # Attribution, privacy, and source policy
│   └── provided-discussion.md         # English synthesis of the supplied discussion
├── docs/
│   ├── README.md                      # Documentation navigation
│   ├── project-structure.md           # This file: ownership and file map
│   ├── problem-statement.md            # Definition and observable failure patterns
│   ├── llm-analysis.md                 # Qualified technical and scientific analysis
│   ├── vibe-coding-analysis.md         # Workflow and lifecycle analysis
│   ├── anti-patterns.md                # Failure patterns and proportionate responses
│   ├── best-practices.md               # Operational guidance
│   ├── agent-adapters.md               # Tool-neutral adapter guidance
│   ├── evaluation.md                   # Scenarios, rubric, and evidence record
│   ├── references.md                   # Background sources and vendor documentation
│   └── examples/
│       ├── tomato-egg.md               # Central public case analogy
│       ├── feature-removal.md          # Removal without historical residue
│       └── scope-boundary.md            # Local correction versus durable preference
└── templates/
    ├── AGENTS.md                       # Minimal copyable repository rule
    ├── task-spec.md                    # Positive task and acceptance template
    └── pr-template.md                  # Final-state PR template for manual reuse
```

## Ownership rules

- `AGENTS.md` and `templates/AGENTS.md` contain the normative rule.
- `README.md` is the bilingual public entry point and should stay concise enough to scan.
- `docs/` contains analysis, examples, guidance, and evaluation material in English.
- `case-materials/` contains sourced or user-supplied evidence and must not silently become normative.
- `templates/` contains reusable artifacts that can be copied into another repository.

When adding a new document, place it under the narrowest applicable directory and add it to `docs/README.md` or this map. Keep the normative rule short; put explanations in the explanatory documents.
