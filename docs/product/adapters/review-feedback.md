# Review adapter contract

Status: MVP defined

vstack does not own a custom visual feedback UI. It integrates task-appropriate tools through a small common contract.

## Direct element feedback

MVP implementation: Orca Design Mode.

Purpose: let the designer point at a rendered element in Orca's browser and send its DOM, computed styles, screenshot, and available source location directly to the active Kilo agent.

This is the shortest polish loop for the MVP: click the element, add intent, let Kilo update the worktree, and inspect the hot-reloaded result.

## Persistent annotation adapter

Extended implementation: Agentation.

Purpose: support persistent, structured, two-way feedback when the effort benefits from an annotation queue, reply threads, lifecycle state, or review across sessions.

The adapter should provide:

- Artifact and page identity.
- Stable annotation identity.
- Element path and available source or component context.
- The designer's comment.
- Intent and severity when supplied.
- Pending, acknowledged, resolved, or dismissed status.
- A reply thread for clarification and resolution summaries.
- A way to list or watch new annotations.

When Agentation is attached, vstack treats it as a live feedback interface during polish. It may watch for, acknowledge, reply to, and address annotations while the designer continues reviewing. It resolves an annotation only after the artifact changes and includes a short resolution summary. Dismissal requires a reason.

## Tuning adapter

Initial implementation: DialKit.

Purpose: let the designer directly manipulate meaningful UI parameters while experiencing the result.

The adapter should provide:

- Named parameter groups tied to the artifact.
- Current, default, and allowed values.
- Continuous, boolean, enumerated, text, color, motion, or action controls as appropriate.
- A serializable accepted state or preset.
- Enough provenance to translate tuned values back into production code.

vstack should expose only meaningful decision axes. It must not turn every CSS value into a dial or use tuning as a substitute for coherent design structure.

## Combined use

Orca Design Mode answers “change this element” with immediate implementation context. Agentation adds a persistent answer to “what feels wrong here?” DialKit answers “what value feels right?” A polish pass may use any combination:

1. The designer points to an element through Orca Design Mode or annotates structural, copy, hierarchy, or behavior problems through Agentation.
2. The designer tunes appropriate spacing, color, motion, or layout parameters.
3. vstack consumes both streams during the active polish loop, asks necessary clarifying questions, and updates the artifact.
4. Feedback statuses, reply threads, and tuning decisions stay attached to the evolving artifact.
5. The loop ends only when the designer accepts the completed effort.

## Adapter boundary

Equivalent tools may replace Orca Design Mode, Agentation, or DialKit if they satisfy the contract. Review adapters are development and review infrastructure, not required product runtime dependencies.

## Completion boundary

There is no required “I have finished annotating, now start changing code” signal. Annotation, agent response, implementation, and re-review may interleave.

The meaningful completion signal is designer acceptance of the artifact. Acceptance transitions vstack from design and polish into delivery to engineering, the requester, or another named recipient.
