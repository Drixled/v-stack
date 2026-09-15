# ADR 0016: Separate repository and minimal MVP

Status: accepted

## Context

vstack coordinates requests, repositories, agents, worktrees, review tools, and publishing. `kilo-design` defines Kilo's design authority. Combining those responsibilities would couple a reusable workflow engine to one organization's design context and make later project agnosticity harder.

The full vision includes proactive Slack intake, project-specific communication, multiple review adapters, and richer effort management. Building all of that before proving the core design loop would create a large integration project instead of a useful first tool.

## Decision

vstack lives in its own repository and consumes `kilo-design` through the Kilo profile or adapter. The repository is the versioned distribution source, not a project the designer must open to begin work. The MVP is installed into Kilo as a dedicated custom agent, one primary skill, and explicit-action workflow commands, then used either inside Orca or from a regular terminal.

The MVP is manually invoked and contains only the smallest complete loop:

1. Receive a freeform, pasted, linked, or attached multimodal design request.
2. Use the repository the designer selected as the target, asking only when the request clearly conflicts with it.
3. In Orca, create the effort directly as a new worktree with the vstack Kilo agent. In a regular terminal, run vstack from an isolated checkout.
4. Load the applicable `kilo-design` context and inspect the implementation.
5. Prepare distinct solution directions and exploratory artifacts when useful.
6. Return the compact direction checkpoint.
7. Implement and polish the chosen direction through a live artifact.
8. Move accepted work to Ready to publish.
9. Publish through an explicit action and prepare the final reply.

Authenticated Slack retrieval, proactive Slack discovery, a standalone dashboard, a custom worktree service, a custom Git UI, additional agent runtimes, and additional host integrations are not required for the MVP.

## Consequences

- The core workflow can be tested before event-driven intake is built.
- `kilo-design` can evolve independently as Kilo's authority.
- The MVP still completes real work end to end rather than demonstrating disconnected commands.
- Integrations can be added behind stable adapter boundaries after the central loop proves useful.
- Orca supplies the polished host path, a regular terminal supplies the fallback path, and Kilo is the only agent runtime required for the MVP.
