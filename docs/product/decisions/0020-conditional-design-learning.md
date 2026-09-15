# ADR 0020: Make design-system learning conditional

Status: accepted

## Context

Some efforts produce a reusable Kilo pattern, clarified design rule, canonical example, or product-specific lesson that belongs in `kilo-design`. Others are one-off copy fixes, local polish, experiments, or implementation details that should not expand the design authority.

Forcing a `kilo-design` update after every effort would add ceremony and pollute the repository with low-value observations. Never suggesting updates would allow useful knowledge to remain trapped in one worktree or the designer's memory.

## Decision

Learning capture is decided per effort.

vstack may suggest a `kilo-design` update when the completed work reveals a reusable pattern, authority clarification, canonical implementation example, or durable lesson. The suggestion is brief and explains why the learning appears reusable.

The designer decides whether to:

- Capture it now.
- Leave it manual for later.
- Ignore it as effort-specific.

vstack never writes to `kilo-design` automatically. When no meaningful reusable learning exists, it does not ask or generate documentation.

## Consequences

- Durable Kilo knowledge can compound across efforts.
- One-off work remains lightweight.
- The designer controls what becomes design authority.
- `kilo-design` avoids becoming an unfiltered activity log.
- Learning capture is optional and separate from whether the product effort is complete.
