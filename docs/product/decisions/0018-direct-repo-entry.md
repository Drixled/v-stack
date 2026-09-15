# ADR 0018: Start directly in the selected repository

Status: accepted

This is the currently implemented startup path. [ADR 0029](0029-request-first-startup.md) proposes repository discovery and an explicit Orca handoff in response to the first real evaluation; that startup change is not implemented yet.

## Context

The designer already works with Kilo's Cloud, Core, Landing, and Design repositories in Orca and knows which repository a request belongs to. A central coordinator session would require opening one agent to open another agent, duplicating Orca's role and adding ceremony before the actual design work begins.

## Decision

vstack starts directly in the repository selected by the designer.

In Orca, the designer creates one new worktree under that repository, selects the vstack Kilo agent, and supplies either a freeform request or a Slack link. That is the only agent session needed for the effort.

In a regular terminal, the designer opens an isolated checkout of the repository and launches Kilo with vstack there.

The current repository is treated as authoritative unless the request clearly conflicts with it. If that happens, vstack asks which codebase to use. It does not produce a routing report or open a coordinator agent.

The separate `vstack` repository exists to version and distribute the agent, skill, commands, references, templates, and integrations. It is not the runtime home of design efforts.

## Consequences

- Orca is opened once and each effort uses one worktree and one Kilo agent.
- The designer's existing repository knowledge is used instead of recreated.
- vstack still detects obvious repository mismatches.
- Self-initiated work and Slack-originated work share the same execution path.
- A future Slack automation can create the same Orca worktree directly without introducing a permanent manager-of-managers.
