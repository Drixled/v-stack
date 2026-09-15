# ADR 0026: Publish from an explicit action inside the Kilo session

Status: accepted

## Context

After the designer accepts an effort, the active vstack agent already knows the change, validation evidence, intended deliverable, and relevant context. Requiring the designer to leave that session and reconstruct the Git and pull-request workflow adds operational work. Automatically publishing on acceptance would remove an important authorization boundary.

## Decision

In a regular terminal, publishing is triggered by an explicit workflow action inside the active Kilo session, provisionally named `/vstack-publish`.

Before requesting authorization, vstack prepares and previews:

- The intended commits and changed-file summary.
- Validation results and any unresolved caveats.
- The target remote and base branch.
- The proposed pull-request title and body.
- The resulting delivery note or requester reply draft.

The designer's explicit invocation authorizes vstack to push the prepared branch and create the pull request. Acceptance of the design alone does not authorize publication.

If publication fails, vstack preserves the isolated branch and prepared metadata, reports the failed step plainly, and offers a safe retry after the underlying problem is corrected. It does not duplicate commits or pull requests on retry.

When Orca is the host, vstack uses Orca's native publishing CTA instead of duplicating it with a second required flow.

## Consequences

- Publication remains deliberate and reviewable.
- The active agent can create accurate PR context without another handoff.
- Terminal and Orca paths share the same authorization boundary while using host-appropriate interfaces.
- Failed publication does not discard completed work or require the designer to reconstruct it.
- The exact command name depends on the supported Kilo workflow-command format and can be finalized during implementation.
