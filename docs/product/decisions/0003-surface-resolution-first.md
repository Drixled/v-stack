# ADR 0003: Resolve the product surface and workspace before designing

Status: accepted

## Context

Kilo has many user-facing surfaces distributed across repositories and packages, including IDE extensions, a web application, browser extensions, a CLI, and a marketing site. A vague request rarely names the correct codebase or implementation boundary.

Opening the right agent workspace is currently the designer’s first bottleneck. Design exploration performed in the wrong workspace will miss runtime behavior, existing components, constraints, and nearby work.

## Decision

Surface resolution is the first mandatory capability after vstack receives design intent.

vstack must:

1. Extract product and interface clues from the request and attached evidence.
2. Consult a maintained surface map.
3. Search plausible workspaces when the map is insufficient.
4. Select the workspace when the answer is sufficiently clear.
5. When it is not clear, ask the designer directly: “Which codebase should I work in?”
6. Locate and trace the relevant implementation before generating solution directions.

The system must support more surfaces than the initial `kilo-code`, `kilo-cloud`, and `kilo-landing` mapping. `kilo-design` is a cross-workspace design authority rather than a product destination. The surface map therefore cannot be a single hardcoded repository switch.

## Consequences

- vstack needs a machine-readable surface registry plus live code search.
- One request may resolve to several packages or repositories.
- Repository identity and product-surface identity remain separate concepts.
- Internal routing may use evidence and confidence, but vstack does not make the designer review a routing report.
- Ambiguous routing produces one direct question instead of a candidate analysis.
- The designer can name or correct the workspace at any point.
- Design generation begins only after the existing implementation is understood.
