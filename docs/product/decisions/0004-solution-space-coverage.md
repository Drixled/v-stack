# ADR 0004: Use solution-space coverage, not a fixed option quota

Status: accepted

## Context

Agents converge quickly on the first plausible answer. Asking for at least five options is a practical defense because it forces continued exploration and often reveals a more elegant solution.

A fixed count is still a weak completion criterion. It can produce cosmetic variations for a narrow copy problem, while five directions may be insufficient for a novel end-to-end experience.

The intended outcome is confidence that the plausible solution space has been considered and that unresolved possibilities are not hiding behind the first acceptable design.

## Decision

vstack uses coverage as the exploration gate.

For every non-trivial design intent, it must:

1. Name the important decision axes before generating directions.
2. Produce directions that occupy materially different regions of that space.
3. Use five directions as the default target when the space is not obviously smaller or larger.
4. Reject options that differ only cosmetically or restate the same strategy.
5. Explain the user, product, and implementation tradeoffs of each serious direction.
6. Continue beyond five when meaningful regions remain unexplored.
7. Stop below five when further directions would be filler and explain why coverage is already sufficient.
8. Select or synthesize the most elegant direction rather than choosing by majority or novelty.
9. Reject directions that lack native fit with the target product, even when they are attractive in isolation.

Prototypes remain conditional. They are created when looking at or using an option will resolve uncertainty that prose, code inspection, or static comparison cannot.

## Consequences

- The exploration artifact includes a design-space map, not only option thumbnails.
- vstack must distinguish strategy from visual variation.
- Every portfolio has an explicit coverage assessment.
- The agent must justify stopping, whether it produces three directions or eight.
- Elegance and native fit are named selection criteria. Their evidence comes from the applicable design authority, shipped product, and implementation constraints.
