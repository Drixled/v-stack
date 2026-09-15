# Direction checkpoint

Status: template

The rendered checkpoint should be concise. Supporting evidence is linked rather than pasted inline.

## Agreed problem or exploration question

One or two sentences describing the intended improvement and agreed scope, or the uncertainty this exploration will answer. If the problem remains unclear, use the problem-framing conversation from ADR 0028 before presenting solution choices.

## Where it lives

- Product surface:
- Workspace:
- Confidence:
- Route or entry point:
- Relevant components:
- Related code or state:
- Applicable `kilo-design` adapter and recipes:

Each item links to the evidence that supports it. Do not dump the complete code trace into the checkpoint.

## What I found

Three to five short findings about the current experience, constraints, known drift, related work, or non-obvious implementation behavior.

## Proposed scope

- Core change:
- Required supporting work:
- Adjacent drift kept out of scope:

## Potential solutions

Show the solution portfolio as a scannable comparison. Each direction includes:

- Name and one-sentence idea.
- What makes it materially different.
- User benefit.
- Main tradeoff.
- Implementation consequence.
- Prototype or visual link when observation is necessary.

State whether coverage is sufficient and why. Present only the materially different directions needed for the decision.

## vstack recommendation

State the recommended direction or synthesis and the evidence behind it. Do not hide behind a neutral list when one direction is stronger.

Recommend whether the next pass should be a prototype or production implementation, and explain why. This is a recommendation, not an automatic commitment.

## What I need from you

Ask only the smallest product, taste, or scope decision that cannot be resolved from available evidence. The designer should be able to answer by steering, combining, rejecting, or reframing directions without reconstructing the discovery work.

Before execution, ask the designer to choose prototype or production code when that is not already clear. For prototypes, name the first visual to review and defer secondary flows until they help answer the design question. Approval of a written direction does not approve its visual execution.

## Expandable evidence

- Source request and provenance.
- Full route and component trace.
- Screenshots and current-state capture.
- Design-space map and coverage assessment.
- Prototype links.
- Technical constraints and test notes.
- Adjacent drift and follow-up candidates.
