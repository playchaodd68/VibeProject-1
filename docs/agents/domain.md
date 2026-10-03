# Domain Docs

This repository uses a **single-context** layout.

## Before exploring or changing the project

- Read root `CONTEXT.md` for resolved domain terminology, when present.
- Read decisions under `docs/adr/` that concern the area being changed, when present.

When these files are absent, proceed silently. The `domain-modeling` skill, used by `grill-with-docs` and `improve-codebase-architecture`, creates them when domain terms or architectural decisions are actually resolved.

## Layout

```text
CONTEXT.md       # Domain glossary, created when terms are resolved
docs/adr/        # Architecture decisions, created when decisions are made
```

Keep `CONTEXT.md` focused on domain language. Record architectural choices and their reasoning as numbered ADRs under `docs/adr/`.

## Use the glossary's vocabulary

Use the terms defined in `CONTEXT.md` in specs, issues, code, tests, and hypotheses. For a missing concept, check whether an existing term already covers it; otherwise surface the gap for `domain-modeling`.

## Surface conflicts with decisions

If a proposal conflicts with an existing ADR, cite that ADR and explain why the decision should be reconsidered before replacing it.

If the project later develops independent bounded contexts, explicitly revisit this layout and introduce a root `CONTEXT-MAP.md` with pointers to the relevant context documents.
