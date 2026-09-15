# Solution-space coverage

Explore meaningfully different strategies, not cosmetic variations of the same layout.

Start from the agreed problem or exploration question. If it is missing, use [problem-framing.md](problem-framing.md) first. A solution portfolio does not substitute for that conversation.

## Coverage test

Exploration is sufficient when:

- The important decision axes are named.
- Plausible solution regions are represented.
- Each serious direction exposes user, product, and implementation tradeoffs.
- Remaining alternatives would be mostly cosmetic.
- The recommendation resolves the problem coherently with minimal concepts, states, exceptions, and implementation burden.

Present only meaningfully different directions needed for the decision. Small copy or UI corrections may need just one recommendation. Broad redesigns may need more investigation but should still present a compact portfolio.

## Conditional subagents

Keep the primary agent alone when the problem is narrow or the decision axes fit comfortably in one context.

Use `vstack-direction` workers when the effort is broad, novel, high-impact, or contains separable solution regions. Assign each worker one distinct region with the same grounded problem and constraints. The primary agent compares, rejects, combines, and recommends. Workers do not commit the product direction.

## Prototypes

Prototype only when observation answers a material question faster or more reliably than prose. Match fidelity to uncertainty:

- Copy: usually no prototype.
- Focused UI adjustment: Storybook or a static variation may be enough.
- Interaction or information-architecture redesign: use a focused interactive artifact.
- Production path already clear: implement directly after designer commitment.

After selecting a direction, build the smallest visual or interaction needed to judge it and return for feedback. Reuse existing primitives and the closest Storybook harness when available. Name the components reused and any simulated or omitted behavior. Do not reproduce every secondary flow, validation rule, or error simulation unless it helps answer the current design question.
