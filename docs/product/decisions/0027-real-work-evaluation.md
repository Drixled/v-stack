# ADR 0027: Validate the MVP through real Kilo work

Status: accepted

## Context

The designer has real, current Kilo design tasks available now. Synthetic benchmark prompts would be easier to control, but they could hide the exact ambiguity, repository constraints, design-system gaps, review friction, and delivery pressure that vstack is intended to handle.

## Decision

The vstack MVP is evaluated through real Kilo tasks from the designer's active workload.

The first evaluation set should include, as real work becomes available:

- A narrow product-copy or UX-writing change.
- A focused UI polish or interaction adjustment.
- A broader experience redesign with meaningful exploration and review.

Each task begins with its original request material rather than a prompt rewritten to help vstack succeed. The run preserves a privacy-safe evaluation record containing the input shape, resolved surface, checkpoint quality, designer interventions, artifact type, polish passes, native-fit findings, delivery outcome, and failures or manual work.

After a real task is completed, its sanitized input and expected workflow properties may be frozen as a repeatable regression case. Synthetic cases are not required before the MVP handles real work successfully.

## Consequences

- MVP validation measures actual usefulness instead of benchmark performance.
- Failures reveal missing product behavior and integration work directly.
- The designer does not need to invent or curate artificial tasks.
- Evaluation records must avoid retaining private Slack content or sensitive attachments unnecessarily.
- Repeatability is added after reality provides the cases, not before.
