# ADR 0013: Isolate every effort in a worktree

Status: accepted

## Context

vstack may create prototypes, Storybook variants, static routes, and other exploratory code before the designer selects a direction. It may also run several efforts concurrently. Using the designer's normal checkout would mix experiments with active work and make rollback, comparison, and abandonment unnecessarily risky.

## Decision

Every vstack effort always runs in its own isolated git worktree and branch.

In Orca, the designer creates the worktree and launches the vstack Kilo agent there as one action. In a regular terminal, the designer starts Kilo from an already-isolated worktree. This applies to exploratory work and production implementation alike. vstack never makes changes in the designer's normal checkout.

## Consequences

- Exploratory code cannot disturb the designer's active checkout.
- Each effort has an independent history and can be reviewed, continued, or abandoned safely.
- Multiple design efforts can run concurrently in the same repository.
- Orca owns worktree creation, branch lifecycle, visibility, and cleanup on the primary host path.
- The terminal path assumes the isolated worktree already exists; automating raw worktree creation is not required for the MVP.
- vstack must track the relationship between a design effort, repository, worktree, branch, agent, and eventual PR or deliverable.
- Completed worktrees may be cleaned up automatically when delivery is confirmed, or retained and archived manually when the designer wants to keep them.
- Cleanup removes the disposable checkout, not the recoverable branch, PR, or delivered artifacts.
