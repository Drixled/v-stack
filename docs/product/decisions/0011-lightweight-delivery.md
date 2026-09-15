# ADR 0011: Delivery is lightweight by default

Status: accepted

## Context

The finished artifact is the primary deliverable. Requiring a full rationale, specification, state inventory, acceptance criteria, and implementation plan for every task would add ceremony after the designer has already judged the work complete. A copy change, UI polish pass, prototype, and full redesign do not need identical packaging.

## Decision

The default delivery package contains:

- The finished artifact, implementation, or PR.
- Brief notes and context needed to orient the recipient.

Nothing else is mandatory.

vstack produces deeper documentation only when:

- The designer asks for it.
- The recipient asks for it.
- The artifact alone leaves consequential behavior or scope ambiguous.
- Engineering cannot implement the result reliably without additional detail.

The designer remains the authority on how much context is enough.

## Consequences

- Delivery effort scales with the actual task instead of a fixed handoff template.
- Small changes stay small.
- Finished work remains easy to pass to engineering or the original requester.
- vstack may recommend extra notes when ambiguity is material, but does not generate them by default.
- A change contract is an optional deliverable, not a required stage.
