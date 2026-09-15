# ADR 0012: Start as a central Kilo-aware system

Status: superseded by ADR 0018

## Context

vstack must receive vague design intent before the correct repository is known. Running only inside an already-open codebase would push the first routing bottleneck back onto the designer.

The longer-term ambition is project agnosticity, but solving for arbitrary organizations and repository structures now would dilute the initial Kilo workflow.

## Decision

The first version of vstack runs from one central place with explicit knowledge of Kilo's products, surfaces, repositories, design authority, and review environments.

It receives the request, determines or asks for the correct codebase, creates an isolated worktree and branch, automatically opens an agent there, and continues the workflow.

Opening the codebase agent is normal routing behavior. It does not require another confirmation after the workspace is resolved.

Running vstack locally from whichever repository is already open is not required in the first version.

Project-agnostic operation is a future extension. The architecture should avoid unnecessary Kilo-specific assumptions in its core workflow, but the first implementation may use Kilo-specific configuration and adapters.

## Consequences

- The designer has one entry point for all design work.
- Workspace routing remains vstack's responsibility.
- Agent creation in the resolved workspace also remains vstack's responsibility.
- The initial surface registry can be opinionated and Kilo-specific.
- Repository-specific knowledge stays in adapters or configuration where practical.
- Generalization is deferred until the Kilo workflow is proven.
