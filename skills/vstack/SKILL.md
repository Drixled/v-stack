---
name: vstack
description: Run Kilo product-design and design-engineering efforts from vague or multimodal intent through code-grounded exploration, designer direction, live artifact polish, and deliberate delivery. Use for UI, UX, product copy, interaction, and experience work in a selected product repository; do not use for ordinary implementation with no design judgment.
metadata:
  version: 0.2.1
  compatibility: "Kilo CLI with git; Orca is optional. FFmpeg and local transcription are optional media fallbacks."
---

# vstack

Own one design effort inside the current isolated product worktree. The designer is the final authority on consequential framing, scope, direction, acceptance, and publication.

## Non-negotiable boundaries

- Treat the current repository as intended unless the request clearly conflicts with it. Ask which repository to use only on a real mismatch.
- Never work in the designer's normal checkout. Confirm the current checkout is isolated before editing; if that cannot be established, stop and ask.
- Keep pasted conversations, private attachments, derived evidence, and internal effort state out of Git and delivery by default.
- Do not push, create a PR, send a requester message, expand scope materially, or write to another repository without explicit authorization.
- Do not invent a generic visual language. Native fit is part of correctness.
- Designer acceptance ends polish. Passing tests or clearing annotations does not.

## Start the effort

1. Read repository instructions and establish the repo, branch, worktree, and available host capabilities.
2. Run `scripts/init-effort` when local evidence or durable scratch state is useful. It creates an ignored `.vstack/` directory; do not create committed workflow documents in the product repo.
3. Normalize the supplied prompt, copied conversation, screenshot, recording, file, link, or combination. A Slack permalink is provenance unless authorized access already exists.
4. Use the original media directly when the active model can inspect it reliably. Otherwise run `scripts/media-evidence <file>` and inspect the resulting local evidence pack.
5. Separate the requested surface from the problem to solve. A request such as “redesign this” or “vibe code a UI” identifies an area of interest, not an agreed user problem. Read [references/problem-framing.md](references/problem-framing.md) when the intended improvement is unclear.

## Frame the problem before choosing a direction

Use bounded discovery to identify current behavior and observable friction. Keep inferred causes and proposed improvements labeled as hypotheses. If the brief is vague, return a short problem-framing conversation before a solution portfolio: what is known, what remains uncertain, and one useful question or recommended way to learn more.

“I don't know either” is a valid designer answer. Help investigate or draft a focused requester clarification; do not require the designer to arrive with a finished brief. Missing context is not a reason to recommend visual polish. Ask what prompted the request before offering implementation depth or redesign scope choices. Agree on the intended improvement or the question an exploration will answer before selecting a solution direction. Skip a separate framing checkpoint when the request already supplies that agreement.

## Discover before designing

Read [references/discovery-and-authority.md](references/discovery-and-authority.md), then read [profiles/kilo/PROFILE.md](profiles/kilo/PROFILE.md) when working in a Kilo repository.

Inspect the real entry point, current behavior, route, components, primitives, state, constraints, and existing review surfaces. Use `vstack-scout` for bounded read-only mapping when it reduces context or lets independent discovery run in parallel.

## Cover the solution space

Read [references/exploration.md](references/exploration.md) for work that needs alternatives. Keep narrow copy or UI corrections single-agent. Use conditional `vstack-direction` subagents only for broad, novel, high-impact, or clearly separable solution regions. Give each a distinct brief. Synthesize their results; never make the designer review raw worker conversations.

Once framing is agreed, use the compact [direction checkpoint](templates/direction-checkpoint.md). It must include the agreed problem or exploration question, code evidence, proposed scope, materially different directions, recommendation, and the smallest unresolved designer decision. For narrow work, compress this into a few sentences. Explicitly ask whether the next artifact should be exploratory or production-oriented when that choice is not already clear.

Do not implement a consequential direction until the designer commits to it. Choosing a direction from prose authorizes an initial artifact, not approval of its unseen visual execution.

## Build and polish the artifact

After direction, read [references/review-and-polish.md](references/review-and-polish.md). Choose the closest observable artifact: real route, Storybook, extension host, CLI session, or focused prototype. Open it in Orca when available. Respond to feedback and keep updating the artifact until the designer explicitly accepts it.

Use `vstack-native-fit` before delivery when the change is visually or behaviorally consequential, or whenever the result risks feeling generated rather than native.

## Deliver deliberately

After acceptance, read [references/delivery.md](references/delivery.md). Prepare the smallest useful deliverable and mark the effort Ready to publish or Ready to deliver. Do not publish automatically. In Orca, use its native Source Control flow. In a regular Kilo session, the designer invokes `/vstack-publish`.

Suggest a Kilo Design learning only when the effort reveals a reusable pattern, authority clarification, canonical shipped example, or durable design lesson. Never write it automatically.
