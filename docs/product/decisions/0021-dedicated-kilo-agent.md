# ADR 0021: Enter through a dedicated Kilo agent

Status: accepted

## Context

The MVP could expose vstack as a command invoked from a regular Kilo session or as a dedicated custom Kilo agent. A command would require the designer to activate the workflow for each task and could allow the session to drift back into generic coding behavior.

The design workflow spans the entire effort, from intake and codebase grounding through options, artifact review, polish, and delivery. It benefits from stable behavior, permissions, and design-specific instructions across turns.

## Decision

The primary MVP entry point is a dedicated custom Kilo agent named `vstack`.

In Orca, the designer creates the effort worktree and selects the vstack Kilo agent. In a regular terminal, the designer launches or selects the same custom agent. The initial message can be a prompt, pasted conversation, attachments, or any combination supported by the intake contract.

Selecting the agent activates the complete vstack workflow for the session. The designer does not need to type `/vstack` first.

Explicit actions such as publishing may still use a workflow command or an Orca control because they represent deliberate authorization boundaries rather than mode activation.

## Consequences

- vstack has a clear, visible entry point in Kilo's agent picker.
- The workflow remains active throughout the design effort.
- Agent-level prompt, model defaults, permissions, and tool access can be configured coherently.
- One primary skill can hold the reusable workflow while the custom agent ensures it is applied.
- A general `/vstack` entry command is not required for the MVP.
