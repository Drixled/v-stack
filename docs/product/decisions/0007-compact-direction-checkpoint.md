# ADR 0007: Use a compact direction checkpoint for designer steering

Status: accepted

Amended by [ADR 0028](0028-problem-framing-before-direction.md): vague requests need a problem-framing conversation before this checkpoint. The direction checkpoint starts from an agreed problem or exploration question.

## Context

The designer wants the agent to complete discovery and return with enough context to confirm the problem and steer solutions quickly. Raw Slack threads, exhaustive repository reports, code-search logs, and long design rationales recreate the work vstack is meant to remove.

Over-compression is also dangerous. The designer needs proof that vstack resolved the correct surface and understood the implementation before trusting its options.

## Decision

The primary post-discovery interface is a compact direction checkpoint.

It contains:

1. A concise statement of the problem vstack believes it is solving.
2. The resolved product surface and workspace, with confidence.
3. Relevant routes, components, code, and applicable design authority.
4. The important current-state findings and constraints.
5. The proposed scope and separated adjacent drift.
6. A covered portfolio of materially distinct solutions.
7. vstack's recommendation and rationale.
8. A recommendation for prototype or production implementation.
9. The smallest unresolved decision requiring designer input.
10. An explicit request for the designer's execution commitment before proceeding.

Detailed evidence remains available through links or expansion but does not dominate the checkpoint.

## Consequences

- vstack synthesizes before asking for review.
- The designer can correct routing or problem framing before expensive implementation.
- Every option remains traceable to code, product context, and design authority.
- Checkpoints optimize for steering, not documentation completeness.
- Full discovery artifacts remain machine-readable for later implementation and audit.
- vstack may recommend an execution medium, but it does not choose prototype versus production code without the designer.
