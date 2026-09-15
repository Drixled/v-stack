# ADR 0006: Keep scope under designer control

Status: accepted

## Context

A focused design task often reveals inconsistent surrounding UI, related flow problems, or shared implementation that could also be improved. The right boundary depends on user impact, product timing, architectural coupling, and the designer's intent.

A fixed “touch only the requested component” rule can produce an incoherent result. Automatic broad cleanup can turn a small task into an uncontrolled redesign.

## Decision

vstack proposes scope; the designer controls it.

Before exploration or implementation, vstack should:

1. Identify the smallest boundary that can resolve the design intent coherently.
2. Include supporting changes that are technically or experientially required.
3. Separate adjacent drift and optional cleanup from the core scope.
4. Explain the user-flow and implementation consequences of including or excluding nearby work.
5. Ask the designer to confirm material expansion when the original intent does not already authorize it.

The scope proposal is advisory. An experienced designer may intentionally choose a narrower patch, a broader cleanup, or a full redesign based on context.

## Consequences

- vstack needs to distinguish required dependencies from attractive cleanup.
- Discovery may be broad while implementation remains focused.
- Adjacent drift becomes a visible follow-up artifact rather than hidden scope.
- The designer does not need to inspect every nearby inconsistency before steering; vstack synthesizes the boundary and tradeoffs.
- No automatic “boil the ocean” principle applies to product-design scope.
