# ADR 0010: Designer acceptance ends polish and triggers delivery

Status: accepted

## Context

Agentation is used during active design and polish. The designer annotates the rendered artifact, the agent responds and changes it, and both can continue the conversation in place. DialKit similarly lets the designer tune the artifact while it is evolving.

Treating annotations as a batch that must be completed before implementation misrepresents this workflow. Implementation and review can interleave until the result is done.

## Decision

The designer's acceptance of the artifact is the completion boundary for the design and polish effort.

Before acceptance, vstack remains in the active polish loop:

- Keep the review artifact available.
- Consume annotations and tuning changes.
- Reply to questions and clarify intent in context.
- Update implementation or prototype as appropriate.
- Resolve addressed annotations with summaries.
- Re-verify affected behavior, states, and native fit.

After acceptance, vstack transitions to delivery:

- Production-ready PR when vstack owns implementation.
- The finished artifact with brief notes and context when engineering will implement.
- A requester-appropriate design deliverable when the recipient is not engineering.

Detailed rationale, specifications, state inventories, acceptance criteria, or implementation plans are included only when the recipient requests them or the work cannot be used safely without them.

## Consequences

- “No pending annotations” is useful state but is not the sole definition of done.
- Designer acceptance is explicit and authoritative.
- vstack does not ask when it should begin acting on Agentation feedback.
- Delivery packaging happens after the artifact is accepted, not before.
- The same polished artifact can support several delivery destinations without forcing a heavyweight handoff package.
