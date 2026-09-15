# vstack glossary

Status: MVP defined. Terms may still evolve during implementation and evaluation.

## Operating system

A coordinated set of principles, workflows, artifacts, tools, and verification gates that governs how an AI agent performs product design and design-engineering work.

## Stack

The complete vstack system. It is not synonymous with a collection of skills.

## Workflow

A repeatable sequence for completing a recognizable product-design or design-engineering job.

## Artifact

Durable structured context produced by one stage and consumed by another. Examples may include a product frame, experience contract, state inventory, prototype comparison, or verification report.

## Evidence

Observable proof used to judge an output, such as runtime behavior, screenshots, interaction traces, accessibility checks, or user-defined acceptance criteria.

## Principle

A durable decision rule that applies across workflows. Principles constrain judgment; they are not procedural steps.

## Design request

The initial request for design help. It may describe a symptom or desired polish without identifying the underlying user problem.

## Product surface

The user-facing environment affected by a request, such as a code editor extension, CLI, web application, or marketing site.

## Execution path

The workflow selected after grounding the request and inspecting the current experience. The initial paths are exploration, direct implementation, and developer handoff.

## Design intent

The grounded expression of what should improve, for whom, why, within what scope, and how the result will be judged.

## Change contract

A build-ready bridge between design and implementation. It specifies behavior, states, relevant data, component boundaries, constraints, and acceptance criteria without prescribing unnecessary implementation detail.

## Signal

An event that may indicate design work, such as a Slack mention, issue, PR comment, or direct request. A signal is not automatically an accepted request.

## Checkpoint

A designed steering moment where vstack presents a compact synthesis, visible options, and the smallest decision it genuinely needs from the designer.

## Direction checkpoint

The first major steering artifact after discovery. It briefly states the understood problem, resolved surface and workspace, relevant routes and code, scope proposal, solution directions, recommendation, uncertainty, and the specific input needed from the designer.

## Execution commitment

The designer's explicit decision about what vstack should produce next. At the first direction checkpoint, this determines whether vstack creates a prototype or moves into production code.

## Review artifact

An observable version of the proposed experience that the designer can inspect and steer. It may be production code, a Storybook story, an interactive browser prototype, an extension build, or another task-appropriate artifact.

## Review surface

The environment used to experience a review artifact. vstack chooses the closest available surface that exposes the behavior and states relevant to the design decision.

## Review adapter

An optional integration that captures structured designer feedback from a review artifact. Agentation is the initial annotation adapter; DialKit is the initial live-tuning adapter.

## Annotation

Feedback attached to a specific rendered element. It carries enough placement, code, intent, severity, and lifecycle context for vstack to address it without guessing what the designer meant.

## Tuning state

The parameter values selected by the designer through a live-control tool. vstack translates an accepted tuning state into maintainable production values rather than shipping a tuning panel as product UI.

## Progressive autonomy

An operating model in which vstack performs safe preparation independently, pauses for consequential human judgment, and regains autonomy after direction is established.

## Polish loop

An iterative cycle of implementation, real-surface inspection, critique, and refinement. It ends when explicit experience evidence satisfies the design intent, not after an arbitrary number of passes.

## Entry source

Anything that supplies design intent to vstack. Entry sources include direct designer prompts, Slack requests, issues, screenshots, and observations made while using the product.

## Surface map

The maintained routing model that connects Kilo capabilities and user-facing surfaces to repositories, packages, components, owners, and runtime environments.

## Surface resolution

The process of determining where a requested experience lives. vstack resolves it autonomously when clear and directly asks which codebase to use when uncertain.

## Solution portfolio

A set of meaningfully different responses that collectively covers the relevant solution space. Five is the default forcing function, not a hard quota. Its members may be copy, UI, interaction, flow, or system-level approaches. It does not require implemented prototypes.

## Prototype

An artifact created to answer a specific visual or behavioral question through observation. It is conditional, not a mandatory stage.

## Design space

The meaningful range of strategies available for resolving a design intent. It is described through decision axes rather than an unstructured list of ideas.

## Decision axis

A dimension on which solutions make materially different choices. Cosmetic variations do not create a new region of the design space.

## Coverage

Confidence that the important decision axes and plausible solution regions have been explored. Coverage prevents premature convergence without requiring filler options.

## Elegance

The quality of resolving the full problem coherently while introducing as few concepts, states, exceptions, and implementation burdens as the experience allows. In vstack, elegance also requires native fit. A clean solution in a foreign visual or interaction language is not elegant.

## Design authority

The ordered sources used to resolve design disagreements. For Kilo, `kilo-design` contains canonical values, generated product artifacts, product adapters, pattern recipes, and decision rationale; real product behavior and shipped examples provide surface-specific evidence.

## Product adapter

Agent guidance for one product surface. It explains how shared Kilo values and principles apply inside that product without pretending every Kilo surface has the same patterns.

## Canonical example

A real shipped implementation used as evidence for a product pattern. Aspirational mockups are not canonical examples.

## Drift

A mismatch between shipped product UI and a higher-authority source such as a canonical token or accepted product rule.

## Native fit

The quality of a solution feeling structurally, visually, verbally, behaviorally, and technically at home in its target product rather than generated in isolation.

## Scope proposal

vstack's evidence-backed recommendation for the smallest change boundary that can produce a coherent result. It separates required supporting work from optional adjacent cleanup.

## Adjacent drift

Inconsistency discovered around the requested surface. vstack reports it as context or a follow-up opportunity; it does not silently add it to the active change.
