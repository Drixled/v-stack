---
description: Preview and deliberately publish an accepted vstack change as a pull request.
agent: vstack
---

Publish only work the designer has already accepted.

1. Confirm this is an isolated git worktree and identify the current branch, remote, and intended base branch.
2. Inspect the full diff, changed files, validation results, and unresolved caveats. Stop if the work is not accepted, contains raw `.vstack/` context, includes unrelated changes, or has an unresolved material failure.
3. Detect whether a pull request already exists for the current branch. Reuse it rather than creating a duplicate.
4. Prepare a publication preview containing the intended commits, changed-file summary, validation evidence, target remote and base, proposed PR title and body, and a short requester reply draft.
5. Show the preview and ask for explicit confirmation before any commit, push, or pull-request mutation.
6. After confirmation, create the intended commit or commits, push the branch, and create or update the pull request. If any step fails, preserve the branch and preview, report the exact failed step, and offer a safe retry that cannot duplicate commits or PRs.
7. Return the PR link and the requester reply draft. Do not send the reply.

When the active effort is hosted in Orca and its native Source Control publishing flow is available, prepare the same preview but direct the designer to the Orca publishing CTA instead of duplicating the push and PR action.

