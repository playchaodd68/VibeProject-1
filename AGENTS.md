# Project instructions

Use the installed `mattpocock-skills` plugin for development. Product scope and technology choices are still to be defined with the user.

## Agent skills

### Issue tracker

Before reading, creating, or updating specs and tickets, read [docs/agents/issue-tracker.md](docs/agents/issue-tracker.md). Work is tracked in GitHub Issues for `playchaodd68/VibeProject-1`.

### Triage labels

Before classifying issues, read [docs/agents/triage-labels.md](docs/agents/triage-labels.md). Use the five default Matt Pocock triage roles.

### Domain docs

Before exploring or changing the project, read [docs/agents/domain.md](docs/agents/domain.md). Use a single-context layout, creating domain documentation as terms and decisions are resolved.

## Working conventions

- Clarify product decisions with the user one question at a time.
- Develop changes on a task branch; use a separate worktree when working concurrently.
- Read the relevant installed skill before applying it. Invoke user-only workflow skills when the user requests that workflow.
- When implementing behavior, use the `tdd` skill at agreed test boundaries and review the completed change before committing.

## graphify

- **graphify** (`~/.Codex/skills/graphify/SKILL.md`) - any input to knowledge graph. Trigger: `/graphify`
- When the user types `/graphify`, invoke the Skill tool with `skill: "graphify"` before doing anything else.
