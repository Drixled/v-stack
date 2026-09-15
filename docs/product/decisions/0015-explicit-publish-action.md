# ADR 0015: Publish through an explicit action

Status: accepted

## Context

Designer acceptance means the design effort is finished, but it should not automatically create external repository state. Pushing a branch and opening a PR are publishing actions with organizational consequences.

Requiring the designer to leave vstack and manually reconstruct the Git workflow would also preserve unnecessary operational work.

## Decision

After the designer accepts a code deliverable, the effort enters a **Ready to publish** state.

vstack moves the effort to Ready to publish. It does not automatically push the branch or create a PR.

In Orca, the designer uses the native Source Control and hosted-review action. In a regular terminal, the designer invokes an explicit publish action inside the active Kilo session. Either action authorizes the push and PR creation. vstack prepares the commit and PR details, then prepares the final Slack reply with the resulting PR link for the designer to review and send. Until publication is triggered, the completed work remains in its isolated worktree.

## Consequences

- Design acceptance and external publication are distinct states.
- The designer controls when repository-visible actions occur.
- Publishing remains convenient and does not require a manual Git handoff.
- vstack reuses Orca's review and publishing UI on the primary path and provides a command trigger for regular terminals.
- vstack must clearly expose whether an effort is polishing, ready to publish, publishing, published, or failed.
- Publishing does not automatically send the final requester communication.
