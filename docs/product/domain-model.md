# vstack domain model

Status: provisional

## Core concepts

| Concept | Meaning |
|---|---|
| Entry source | The origin of design intent, such as a direct prompt, Slack mention, issue, screenshot, or observation by the designer. |
| Signal | An observable event that may contain a design request, such as a Slack mention. |
| Candidate request | A signal classified as potentially actionable but not yet accepted as design work. |
| Design request | The initial, usually vague request for UX or UI help. |
| Requester | The teammate asking for a product change or design intervention. |
| Product surface | The user-facing environment affected by the request. |
| Surface map | A maintained mapping between product capabilities, interface surfaces, repositories, packages, owners, and runtime environments. |
| Workspace | The product codebase in which a resolved surface is implemented. |
| Workspace candidate | A workspace that may contain the requested surface, paired with evidence and confidence. |
| Surface resolution | The process and decision that connect design intent to the correct product surface and workspace. |
| Design context | Existing principles, patterns, constraints, decisions, and reusable product knowledge. |
| Design authority | The ordered set of prescriptive and descriptive sources that determines whether a solution belongs in a Kilo product. |
| Product adapter | Surface-specific agent guidance that translates shared Kilo values into the patterns, constraints, and behavior of one product. |
| Canonical example | A real shipped implementation that provides evidence for an accepted product pattern. |
| Drift | A mismatch between shipped UI and a higher-authority design source. |
| Native fit | The degree to which a solution looks, behaves, reads, and is implemented as a coherent part of its target product. |
| Scope proposal | The smallest coherent change boundary suggested by vstack, including required dependencies and explicitly separated adjacent opportunities. |
| Adjacent drift | Relevant inconsistency discovered near the requested change that is not automatically part of the work. |
| Current experience | The actual behavior and interface that users encounter before the change. |
| Design intent | A grounded statement of the user problem, desired outcome, scope, and constraints. |
| Execution path | The selected way of resolving the request: explore, implement directly, or prepare a developer handoff. |
| Exploration | A bounded comparison of meaningfully different approaches. |
| Design space | The meaningful set of alternative strategies and decisions available for resolving a design intent. |
| Decision axis | A dimension along which materially different solutions can vary. |
| Solution portfolio | A set of distinct directions that collectively covers the meaningful design space. Five is the default exploration target, not a hard completion rule. |
| Coverage assessment | Evidence that the important decision axes and plausible solution regions have been explored without padding the portfolio with cosmetic variations. |
| Elegance assessment | A judgment of how completely and coherently a direction resolves the problem relative to the concepts, states, exceptions, and implementation cost it introduces. |
| Variant | One testable design or interaction direction within an exploration. |
| Prototype | A disposable or production-adjacent artifact used only when observing a proposed behavior or interface will resolve meaningful uncertainty. |
| Design decision | The selected direction and the rationale for choosing it. |
| Change contract | A build-ready description of behavior, states, data, components, constraints, and acceptance criteria. |
| Change set | The implementation produced from the selected decision or change contract. |
| Evidence | Observable proof that the result satisfies the design intent. |
| Delivery | The implementation, developer handoff, and/or PR that completes the workflow. |
| Learning | A durable insight returned to design context for future work. |
| Checkpoint | A bounded moment where the agent presents synthesized evidence and asks for consequential human judgment. |
| Direction checkpoint | The compact review packet that confirms problem understanding, routing, implementation findings, scope, solution directions, and the next decision. |
| Execution commitment | The designer's explicit choice of what vstack should produce next, beginning with prototype or production implementation. |
| Review artifact | An observable version of the proposed experience prepared for designer inspection and steering. |
| Review surface | The environment in which the artifact is experienced, such as the real application, Storybook, an extension host, a browser prototype, or a CLI session. |
| Review adapter | A tool integration that turns designer interaction with a review artifact into structured input vstack can consume. |
| Annotation | Element-scoped feedback with intent, severity, context, status, and optional conversation. |
| Tuning state | A set of designer-controlled parameter values captured while manipulating the artifact. |
| Polish loop | Repeated execution, inspection, critique, and refinement after a direction is established. |

## Relationships

```text
Entry source provides Design intent or Signal
Signal may become Candidate request
Requester creates Design request
Candidate request is accepted or dismissed as Design request
Design request targets Product surface
Surface map proposes Workspace candidates
Surface resolution confirms Product surface and Workspace
Product surface selects Product adapter and Design authority
Workspace and Design authority reveal Current experience and Drift
Current experience plus Design request become Design intent
Design intent selects Execution path
Exploration maps Design space and Decision axes
Exploration produces Solution portfolio
Coverage assessment determines whether Solution portfolio is sufficient
Prototype tests selected uncertainty when needed
Design decision selects or synthesizes Variants using Elegance assessment
Design decision becomes Change contract
Change contract guides Change set or developer handoff
Evidence verifies Change set against Design intent
Native fit verifies Change set against Design authority
Scope proposal exposes Adjacent drift to designer judgment
Delivery packages Change set, Design decision, and Evidence
Delivery produces Learning
Learning updates Design context
Checkpoint connects agent preparation to designer judgment
Direction checkpoint packages discovery and Solution portfolio for rapid steering
Execution commitment authorizes Prototype or production Change set
Change set produces Review artifact in Review surface
Review adapter captures Annotation or Tuning state
Designer judgment steers Polish loop through Review artifact
Polish loop refines Change set until Evidence satisfies Design intent
```

## Remaining implementation boundaries

- How vstack detects applicable finalized token artifacts and functioning product skills across product worktrees.
- How native media capability is detected and which fallback inspection tools are available in each supported host.
- The exact Kilo workflow-command syntax for the accepted in-session publication flow.
- Which real active tasks first prove the workflow across copy, small UI work, and redesigns, and how their inputs are sanitized for later regression use.
