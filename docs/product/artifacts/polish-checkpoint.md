# Polish checkpoint

Status: template

The artifact is the checkpoint. The text around it only helps the designer enter the right state and understand what changed.

## Open the artifact

- Review surface:
- Artifact link or launch command:
- Scenario currently loaded:
- What changed since the previous pass:
- Feedback adapter: Agentation, equivalent annotation tool, or none
- Tuning adapter: DialKit, equivalent live-control tool, or none

## Inspect these states

List only the states relevant to this pass. Link or provide direct controls when possible.

- Primary path:
- Important alternative path:
- Loading or disabled state:
- Empty or error state:
- Responsive or host-specific state:
- Keyboard and focus behavior:

## What vstack checked

- Behavior against design intent.
- Native fit against the applicable product authority.
- Relevant states and edge cases.
- Responsive and accessibility behavior where applicable.
- Known limitations or evidence still missing.

## What changed

A short before-and-after summary. Do not replace the review artifact with screenshots or prose when the interaction itself matters.

## What I need from you

The designer reacts directly through the artifact: annotate what feels wrong, tune appropriate values, ask questions, approve parts, or continue steering.

When Agentation or an equivalent is active, vstack reads, acknowledges, replies to, and resolves element-level annotations during the active polish loop. It does not wait for a separate batch-complete signal. When DialKit or an equivalent is active, preserve the chosen parameter state or exported preset so vstack can translate it into production values.

The loop ends when the designer says the effort is done and accepts the artifact. At that point, vstack prepares the appropriate delivery rather than asking for another feedback pass.
