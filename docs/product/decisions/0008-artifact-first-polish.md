# ADR 0008: Review and polish through an experience artifact

Status: accepted

## Context

Product and interaction quality cannot be judged reliably from an agent's implementation summary. Screenshots are insufficient when timing, focus, state transitions, responsiveness, keyboard behavior, or host integration matter.

The designer wants to review an artifact in a browser, Storybook, or whatever environment best represents the changed experience.

## Decision

Every polish checkpoint is anchored to a review artifact opened in the closest useful review surface.

vstack selects the surface that makes the relevant behavior observable, preferring the real product runtime when practical. Depending on the task, the artifact may be:

- A real application route in the browser.
- A Storybook story or component harness.
- An extension development host.
- A live CLI or terminal session.
- An interactive local prototype.
- A static comparison only when the decision is genuinely non-interactive.

The artifact must expose the states relevant to the change. vstack provides a short orientation and verification summary but does not substitute prose for experience.

## Consequences

- “Implemented” and “ready for designer review” are separate states.
- vstack needs surface-specific launch and inspection adapters.
- Storybook is useful but is not the universal review environment.
- Interactive work cannot be approved solely from a screenshot.
- The designer steers successive passes by reacting to the artifact.
- Completion requires both automated evidence and designer acceptance of the experienced result.
