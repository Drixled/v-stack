# ADR 0005: Treat kilo-design as design authority, not a product workspace

Status: accepted

## Context

AI-generated interfaces often solve the requested task while introducing a generic, “vibed” visual and interaction language. They look polished in isolation but do not belong in the codebase or product.

`kilo-design` exists to prevent each Kilo surface and agent from inventing its own system. Product code does not live there. The repository provides canonical values, generated product artifacts, product-specific agent guidance, evidence-led pattern recipes, and design decision records.

The authority model distinguishes two kinds of truth:

- Values such as tokens are prescriptive. Shipped code that disagrees is drift.
- Patterns are descriptive but evolving. They must be grounded in canonical examples from real shipped product code rather than invented ideals.

## Decision

After vstack resolves the product surface and workspace, it must load the strongest applicable and sufficiently mature `kilo-design` authority before exploration or implementation. Finalized token artifacts are always usable. Product skills are loaded only when they function for the resolved surface; otherwise vstack falls back to shipped product evidence and reports the missing guidance as a coverage gap.

The authority chain is:

1. The designer’s explicit goal and approved direction.
2. Real product behavior and implementation constraints.
3. Canonical token sources and generated product artifacts.
4. The applicable product adapter.
5. Matching pattern recipes.
6. Canonical examples in shipped product code.
7. Nearby shipped UI.
8. General interface heuristics.

The chain is not a license to reproduce existing drift. Prescriptive values override conflicting shipped values. Product patterns require shipped evidence or must be reported as a coverage gap.

## Native-fit verification

Every selected direction and delivered change is checked for:

- Token and semantic-role fidelity.
- Use of existing primitives and host-native behavior.
- Consistency with product-specific patterns and canonical examples.
- Voice, nouns, hierarchy, density, and visual character.
- Interaction states, accessibility, responsiveness, keyboard behavior, and motion.
- Added concepts, exceptions, and one-off styling.
- Deliberate deviations and unresolved coverage gaps.

Passing generic UI heuristics is insufficient.

## Consequences

- `kilo-design` participates in every product-UI workflow as context, not as the implementation destination.
- vstack needs surface-specific product adapters rather than one universal visual recipe.
- New patterns are not invented in the authority repo before they exist in shipped product code.
- A missing rule becomes a visible coverage gap, not permission to generate generic UI.
- An unfinished or unavailable product skill does not block work on that surface.
- Native fit is a required verification result alongside behavioral correctness.
- Focused work identifies surrounding drift but does not automatically absorb it into scope.
