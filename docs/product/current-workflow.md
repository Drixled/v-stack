# Current Kilo design workflow

Status: observed

## Trigger

A teammate asks the sole product designer for help. The request is usually underspecified, such as “this needs better UX” or “polish this UI.”

## Current sequence

1. Interpret the vague request enough to identify the affected product surface.
2. Choose and open an agent in the relevant workspace.
3. Prompt the agent with the design problem, often still expressed informally.
4. Ask the agent to explore the codebase and locate the relevant components and behavior.
5. Decide whether the task needs divergent exploration, direct design work, implementation, or a developer plan.
6. When exploration is needed, use Paper.design through MCP to generate many UI directions, or create static variations directly in Storybook.
7. Apply designer judgment to select and refine a direction.
8. Implement it with production-quality code, or produce an implementation plan for a developer.
9. Prepare or write the PR.

## Workspace routing

| Surface | Primary workspace |
|---|---|
| VS Code extension, JetBrains extension, CLI | `kilo-code` |
| Web application | `kilo-cloud` |
| Marketing site | `kilo-landing` |

`kilo-design` is not a product-code destination. It is the cross-workspace authority for tokens, generated artifacts, product-specific agent guidance, pattern recipes, and the rationale behind design decisions.

## Current strengths

- The designer retains product and quality judgment.
- Agents can ground design work in the actual implementation.
- Exploration can happen visually in Paper.design or close to production in Storybook.
- The workflow can end in code, a developer-ready plan, or a PR.

## Current failure points

- The initial problem, user impact, evidence, constraints, and desired outcome are implicit.
- Workspace routing and relevant context live in the designer’s head.
- The agent may receive a solution-shaped instruction before understanding the experience.
- The choice between Paper.design, Storybook, direct implementation, and handoff is ad hoc.
- Exploration criteria and selection rationale are rarely durable artifacts.
- “Best quality possible” is not an explicit, repeatable verification contract.
- The implementation and developer-handoff paths can produce different levels of completeness.
- The PR closes the work, but there is no explicit learning loop back into design context.

## Candidate vstack transformation

```text
Vague request
  -> clarify intent and evidence
  -> identify surface and load workspace context
  -> inspect the current experience and implementation
  -> choose an execution path
  -> explore and select, or proceed directly
  -> implement or produce the appropriate artifact
  -> verify the real experience
  -> deliver it with brief notes and context
  -> add deeper documentation only when requested or necessary
```

## Target operating model

The designer starts the first version directly in the known repository by selecting the dedicated vstack Kilo agent, either in a new Orca worktree or from an isolated checkout in a regular terminal. The request may come from Slack or directly from the designer:

```text
Pasted Slack content, optional source link, prompt, screenshot, video, file, or designer impulse
  -> normalize the design intent
  -> use the repository selected by the designer
  -> ask which codebase to use only when the request conflicts with the current repository
  -> run Kilo with vstack in the isolated Orca worktree or terminal checkout
  -> load the applicable kilo-design authority and nearby canonical examples
  -> locate and understand the relevant implementation
  -> propose the smallest coherent scope and surface adjacent drift
  -> map the meaningful solution space
  -> use independent Kilo subagents only when the effort benefits from parallel exploration
  -> generate distinct directions until coverage is sufficient
  -> create exploratory prototypes or Storybook variants when useful
  -> compact designer direction checkpoint
  -> designer chooses prototype or production implementation
  -> create the closest reviewable experience artifact
  -> repeated artifact review, polish, and verification
  -> verify native fit against the product's design authority
  -> designer accepts the completed effort
  -> enter Ready to publish
  -> designer triggers publishing when external repository action is needed
  -> deliver the PR or artifact with brief notes and context
  -> add deeper documentation only when requested or necessary
  -> optionally suggest reusable learning for kilo-design when the effort produced any
```

## Task scale

The same workflow must contract or expand with the problem:

- UX copy may need contextual inspection, several materially different copy strategies, and no prototype.
- A small UI adjustment may need structural or visual directions with lightweight static comparison.
- A full experience redesign may need flow modeling, interaction prototypes, implementation architecture, and several polish cycles.

The workflow is stable. The cost of each stage is proportional to uncertainty and impact.

The initial implementation is intentionally Kilo-specific. Project-agnostic operation is a future extension after this workflow is proven.

The MVP is manually invoked through Kilo inside Orca or a regular terminal. The separate `vstack` repository is only the installable workflow source. Orca owns worktrees, agent terminals, browser previews, diffs, and publishing when it is the host. Proactive Slack intake and a standalone dashboard are outside the initial loop.

## Direction checkpoint

After discovery and exploration, vstack returns a compact decision packet rather than a long report. It should let the designer confirm the problem, verify the routing, understand what was found, compare the solution directions, and steer the next pass in a few minutes.

The summary stays small. Code traces, screenshots, prototypes, and detailed evidence remain linked and expandable.

## Native-fit gate

A result is not ready merely because it works or looks polished in isolation. Before delivery, vstack must verify that it belongs in the target product:

- Values follow canonical tokens and semantic roles.
- Existing primitives and host-native behavior are reused when appropriate.
- Product patterns are grounded in shipped canonical examples.
- Voice, product nouns, information density, and interaction behavior match the surface.
- Required states, accessibility, responsive behavior, and keyboard behavior are complete.
- Any deliberate deviation is named and justified.
- Surrounding drift is identified without silently expanding the requested scope.
- The designer confirms any material scope expansion.

## Polish loop

The polish loop happens through a reviewable artifact, not through an implementation report:

```text
Build or update artifact
  -> open it in the closest useful review surface
  -> attach annotation and/or live-tuning adapters when useful
  -> designer inspects, annotates, tunes, and steers
  -> vstack responds and changes the artifact during the active loop
  -> verify affected states and native fit
  -> repeat until the designer accepts it
```

The review surface depends on the work. It may be a real browser route, Storybook story, extension development host, CLI session, local prototype, or another environment where the changed experience can actually be observed.

Orca Design Mode is the default direct element-to-agent feedback path for the MVP. Agentation is added when the work needs persistent structured annotations, lifecycle state, or feedback across sessions. DialKit is the preferred live-tuning adapter when the designer needs to manipulate continuous or enumerated UI values. They can be used independently or together.

Finishing the Agentation or tuning session does not begin implementation. It marks the end of the design and polish effort. Once the designer accepts the artifact, vstack transitions to delivery.

## Delivery default

Delivery is intentionally lightweight. vstack sends the finished artifact or PR with enough notes and context for the recipient to understand what changed and why. It does not automatically generate a design rationale, formal specification, state inventory, acceptance criteria, or implementation plan.

Those materials are created only when the designer or recipient requests them, or when omitting them would make the result ambiguous or unsafe to implement. The amount of ceremony follows the work; the work does not expand to satisfy a handoff template.

## Exploration completion rule

Five options are the default forcing function, not the definition of completion. Exploration stops when:

- The important decision axes have been named.
- The plausible regions of the solution space have been represented.
- Remaining ideas are minor variations rather than different strategies.
- Every serious direction has explicit user, product, and implementation tradeoffs.
- The selected or synthesized direction can be explained as more elegant than the alternatives.

A narrow problem may reach coverage with fewer than five directions. A novel or high-impact problem may require more.
