# Discovery and authority

The goal is enough evidence to frame the problem and compare real solution regions, not an exhaustive repository report.

## Establish the surface

- Read repository and nested agent instructions first.
- Identify the current repo from its remote, package metadata, and folder structure.
- Resolve the user-visible entry point and the owning surface inside the repo.
- If the request and current repository genuinely conflict, ask which codebase to use before editing.

## Trace the implementation

Find and inspect only what changes the design decision:

- Route, command, view, modal, screen, or host entry point.
- Owning components and primitives.
- State, data, permissions, and validation that shape behavior.
- Existing copy and product terminology.
- Important loading, empty, error, disabled, responsive, keyboard, and host states.
- Storybook, development-host, preview, or test commands that can expose the experience.
- Closest shipped comparable behavior.

Prefer live code search over remembered paths. Link evidence in the direction checkpoint instead of pasting search traces.

## Propose scope

Separate:

- Core change required to solve the problem.
- Supporting work required for coherence.
- Adjacent drift or cleanup that remains out of scope.

Do not silently broaden the change because nearby UI is inconsistent.

