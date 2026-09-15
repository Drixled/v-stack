# ADR 0017: Kilo executes vstack and Orca is the primary host

Status: accepted

## Context

Orca is a worktree-native desktop environment for running AI coding agents. It already owns isolated workspaces, agent terminals, browser tabs, diff review, worktree status, commit and push flows, and hosted review creation. Orca also includes Kilocode as a supported agent.

Kilo provides the agent runtime vstack needs: CLI execution, custom agents, skills, workflows, MCP integrations, permissions, and code changes inside the current project.

Reimplementing Orca's environment and Git lifecycle inside vstack would make the MVP larger while producing a worse integration with the designer's actual working environment.

## Decision

Kilo is the only agent runtime required for the vstack MVP. Orca is the polished primary host, and a regular terminal is the minimal fallback host.

vstack remains a separate repository, but its first distributable form is a Kilo-compatible workflow package rather than a standalone application. It contains:

- A custom primary vstack agent that is the normal session entry point.
- Agent Skills for the design workflow and checkpoints.
- Kilo workflow commands only for explicit authorization actions such as publishing.
- The Kilo surface profile and repository routing configuration.
- Prompt and artifact templates.
- Thin Orca integration for worktrees, review surfaces, effort status, and publishing.
- A terminal path that runs the same vstack workflow from an already-isolated checkout.

The MVP does not rely on Kilo's deprecated legacy Orchestrator agent. The vstack Kilo agent provides design reasoning and workflow behavior inside one effort. A runtime Kilo plugin is deferred until vstack needs event hooks or capabilities that skills and workflow commands cannot provide.

Orca owns:

- Project registration and repository locations.
- Worktree and branch creation.
- Agent terminals and lifecycle visibility.
- Browser tabs and native Design Mode.
- Diffs, commits, pushes, and pull-request composition.
- Worktree cleanup and archival.

Kilo inside the target Orca worktree owns:

- Codebase inspection and implementation tracing.
- Loading vstack and `kilo-design` context.
- Solution-space exploration.
- Creating prototypes or production changes.
- Verification and responding to designer feedback.
- Preparing PR and delivery copy.

vstack owns the process joining those capabilities:

- Surface routing.
- Design-specific discovery and coverage.
- Direction checkpoints.
- Native-fit requirements.
- Artifact-first polish.
- Designer acceptance and Ready to publish state.

## MVP topology

```text
Orca path
  -> designer creates a worktree in the known repository
  -> Orca launches Kilo with vstack in that worktree
      -> vstack guides discovery, exploration, and polish
      -> kilo-design supplies design authority
      -> Orca browser / Design Mode exposes the live artifact
      -> Orca diff and Source Control handle publication

Terminal path
  -> designer opens an isolated checkout of the known repository
  -> designer launches Kilo with vstack
  -> the same design workflow runs without Orca-specific UI
```

## Consequences

- The MVP does not need its own desktop app, dashboard, worktree service, terminal manager, browser, or Git UI.
- The MVP does not need a custom TypeScript Kilo plugin.
- Orca's worktree metadata and comments can expose lightweight effort status without a new database.
- Orca Design Mode is the default element-to-agent feedback path for the MVP.
- Agentation remains useful when persistent, structured, two-way annotation sessions are needed beyond Orca's direct click-to-agent loop.
- DialKit remains useful for live parameter tuning.
- Codex, Claude Code, Super, and other agent or host integrations are explicitly outside the MVP.
