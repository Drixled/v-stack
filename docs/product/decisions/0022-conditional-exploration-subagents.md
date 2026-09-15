# ADR 0022: Scale exploration with conditional subagents

Status: accepted

## Context

A copy adjustment or small UI fix does not need several agents. A larger interaction redesign may benefit from independent perspectives that explore genuinely different regions of the solution space. Always spawning agents would add cost and coordination noise; never doing so could reduce coverage on consequential work.

## Decision

The primary vstack agent decides whether exploration should remain single-agent or use parallel Kilo subagents.

Use the primary agent alone when the problem is narrow, the decision axes are limited, or materially different directions can be covered efficiently in one context.

Use independent subagents when the effort is broad, novel, high-impact, or contains separable solution regions that benefit from independent reasoning or prototypes.

When subagents are used:

- Each receives a distinct exploration brief or decision region.
- They do not independently commit the product direction.
- The primary vstack agent compares and synthesizes their work.
- The designer sees one coherent direction checkpoint rather than several raw agent conversations.

## Consequences

- Small work stays fast and inexpensive.
- Larger work gains genuine divergence instead of cosmetic option padding.
- The primary vstack agent remains the designer's single point of contact.
- Agent count is an execution choice, not a visible workflow requirement.
- Exploration still stops according to coverage, not according to how many agents ran.
