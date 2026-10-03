# Issue tracker: GitHub

Specs, tickets, and issue discussions live in [playchaodd68/VibeProject-1](https://github.com/playchaodd68/VibeProject-1/issues). Use the authenticated `gh` CLI from this clone; the connected GitHub plugin can perform equivalent supported operations.

Run `git remote -v` to confirm the repository. Outside the clone, pass `--repo playchaodd68/VibeProject-1` to `gh issue` and `gh pr` commands.

## Conventions

- **Create**: `gh issue create --title "..." --body-file <file>`. Write multiline text to a UTF-8 file first.
- **Read**: `gh issue view <number> --json number,title,body,state,labels,comments`.
- **List**: `gh issue list --state open --limit 100 --json number,title,body,labels,assignees`, with relevant label filters. When completeness matters, use `gh api --paginate 'repos/playchaodd68/VibeProject-1/issues?state=open&per_page=100'` and exclude objects containing `pull_request`.
- **Comment**: `gh issue comment <number> --body-file <file>`.
- **Labels**: `gh issue edit <number> --add-label "..." --remove-label "..."` as appropriate. Use the mapping in [triage-labels.md](triage-labels.md).
- **Close**: post the resolution, then `gh issue close <number>`.

When a skill says **publish to the issue tracker**, create a GitHub issue. When it says **fetch the relevant ticket**, read the issue body, labels, and comments.

GitHub shares a number space between issues and pull requests. For an ambiguous reference, resolve its resource type with `gh api repos/playchaodd68/VibeProject-1/issues/<number>`; the presence of `pull_request` identifies a PR. Fetch its diff when needed.

## Pull requests as a triage surface

**PRs as a request surface: no.**

Development changes can use pull requests. Incoming PRs are excluded from the issue triage queue under this setting.

## Wayfinding operations

Used when the user invokes `wayfinder`.

- **Labels**: before first use, list repository labels and create only missing `wayfinder:map`, `wayfinder:research`, `wayfinder:prototype`, `wayfinder:grilling`, and `wayfinder:task` labels. Preserve existing label definitions.
- **Map**: one issue labelled `wayfinder:map`, holding Notes / Decisions-so-far / Fog.
- **Child ticket**: an issue labelled `wayfinder:<type>` (`research`, `prototype`, `grilling`, or `task`). Link it as a GitHub sub-issue. When sub-issues are unavailable, use a task list in the map body and `Part of #<map>` at the top of the child body.
- **Blocking**: use GitHub native issue dependencies. Add an edge with `gh api --method POST repos/playchaodd68/VibeProject-1/issues/<child>/dependencies/blocked_by -F issue_id=<blocker-db-id>`. Obtain the numeric database ID with `gh api repos/playchaodd68/VibeProject-1/issues/<blocker> --jq .id`; it is different from the issue number and `node_id`. When dependencies are unavailable, place `Blocked by: #<n>, #<n>` at the top of the child body.
- **Frontier**: list the map's open children and exclude assigned issues or those with open blockers. Check `issue_dependencies_summary.blocked_by`, or resolve the fallback body links. Select the first eligible issue in map order.
- **Claim**: `gh issue edit <number> --add-assignee @me` as the session's first write.
- **Resolve**: post the result, close the child, then add a concise result and link to the map's Decisions-so-far.
