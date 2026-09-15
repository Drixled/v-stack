# ADR 0009: Integrate existing review tools through adapters

Status: accepted

## Context

The designer already uses Agentation for element-level feedback and DialKit for direct UI tuning. Building another proprietary annotation or tuning interface inside vstack would duplicate working tools and slow the core workflow.

The tools solve different problems. Agentation turns annotations into agent-readable context and supports a feedback lifecycle. DialKit wires live controls directly to UI values for rapid visual, layout, and motion tuning.

## Decision

vstack integrates review tools through optional adapters.

- Agentation is the initial annotation adapter.
- DialKit is the initial tuning adapter.
- They may run independently or together.
- Equivalent tools can replace them if they implement the same conceptual contract.
- vstack remains responsible for choosing useful controls, synthesizing feedback, applying coherent changes, updating the artifact, and preserving the decision trail.

vstack does not build its own annotation canvas or generic parameter panel in the initial system.

## Consequences

- Browser and Storybook artifacts can support precise element-level feedback through Agentation.
- Agentation's MCP lifecycle can drive acknowledgement, clarification, resolution, and watch-based interaction throughout the active polish loop.
- DialKit can expose intentional decision axes for designer tuning and export the accepted state.
- Tool setup is surface-specific and remains optional.
- Review infrastructure must stay out of production builds unless explicitly intended.
- Captured feedback and tuning state become inputs to the same polish loop rather than separate workflows.
- vstack does not impose a batch-complete ceremony on Agentation feedback.
