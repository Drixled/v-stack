# ADR 0024: Consume Kilo Design according to surface maturity

Status: accepted

## Context

`kilo-design` is the canonical source for Kilo tokens and product guidance, but its outputs do not all have the same maturity. The tokens and generated product artifacts are established. Agent-facing product skills are still being proven, with functioning guidance currently concentrated on web work. Requiring a finalized product skill for every surface would block Editor, JetBrains, CLI, and other work that vstack must support.

## Decision

vstack consumes the strongest available `kilo-design` authority for the resolved surface without assuming every product skill exists or is ready.

For every product-UI effort:

1. Use the applicable finalized token source or generated product artifact.
2. If a functioning product skill is installed for the target surface, invoke its path-scoped router and load only the relevant overlay, reference, and recipe.
3. If no functioning product skill exists, inspect the target product's shipped components, host-native conventions, and nearby behavior directly.
4. Treat missing product guidance as a visible coverage gap, not as a blocker and not as permission to produce generic UI.
5. Never load unfinished skill sources as authoritative guidance merely because they exist in the `kilo-design` repository.

vstack detects and consumes available Kilo Design material. It does not silently install, update, finalize, or publish Kilo Design skills. Reusable lessons may still be suggested for later capture under the existing conditional-learning policy.

## Consequences

- vstack can support every Kilo surface before every product skill is finalized.
- Finalized tokens retain prescriptive authority across surfaces.
- Working web guidance is used where it is actually applicable.
- Product code and host conventions provide the fallback evidence for uncovered surfaces.
- Gaps in Kilo Design become useful signals without stopping the active design effort.
- Kilo Design lifecycle and publication remain separate from vstack installation.
