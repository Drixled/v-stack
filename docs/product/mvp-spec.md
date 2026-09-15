# vstack MVP specification

Status: build-ready product definition

## Product definition

vstack is an opinionated product-design and design-engineering workflow for Kilo agents.

It helps Kilo's sole designer turn an informal request or self-initiated improvement into a grounded, native, polished artifact or implementation without repeatedly reconstructing the codebase, design context, exploration method, and delivery process.

vstack is not:

- An agent manager. Orca already fills that role on the primary host path.
- A design system. `kilo-design` remains the Kilo design authority.
- A standalone dashboard or request tracker.
- A generic collection of loosely related skills.
- An autonomous replacement for designer judgment.

## First user and problem

The first user is Kilo's sole product designer.

Requests commonly arrive through Slack as vague messages with partial context, screenshots, recordings, or references. Work may also begin directly when the designer notices something worth improving.

The recurring burden is maintaining context across many requests while repeatedly teaching a fresh agent how to:

- Understand the actual problem.
- Work in the existing product and implementation.
- Use Kilo's design authority.
- Explore enough of the solution space.
- Produce a reviewable artifact.
- Respond to design feedback and keep polishing.
- Deliver the finished work appropriately.

## MVP form

vstack is distributed from its own repository and installed into Kilo as:

- A dedicated custom primary agent named `vstack`.
- One primary Agent Skill containing the end-to-end workflow.
- Supporting references and artifact templates.
- A Kilo-specific product profile that locates `kilo-design` and relevant Kilo context.
- Explicit workflow commands for authorization boundaries such as terminal publishing.
- A thin Orca adapter for status and review conveniences.

A repository setup command installs or updates these pieces together, validates the local configuration, and provides a clean removal path. A formal Kilo plugin or marketplace package is not required for the MVP.

The distribution repository is not opened to start ordinary design work.

## Supported environments

### Primary: Orca and Kilo

1. The designer selects the known Kilo repository in Orca.
2. The designer creates a new worktree and selects the vstack Kilo agent.
3. The designer provides the request and available context.
4. One vstack agent owns the effort in that worktree.

Orca owns worktree creation, branches, terminals, browser previews, Design Mode, diffs, Source Control, pull-request composition, and cleanup.

### Fallback: regular terminal and Kilo

1. The designer opens an already-isolated checkout of the known repository.
2. The designer launches or selects the vstack Kilo agent.
3. The same core workflow runs without Orca-specific UI.

Automating raw worktree creation for the terminal path is not required for the MVP.

## Intake contract

The initial message has no required form. It can contain any useful combination of:

- A freeform prompt.
- Copied Slack message or thread text.
- Images or screenshots.
- A screen recording or video.
- Local files.
- Web links.
- An optional Slack permalink.

A Slack permalink is provenance unless authorized Slack access already exists. The MVP does not bypass Okta, reuse browser credentials, scrape authenticated Slack, or depend on enterprise OAuth.

When essential content is missing, vstack asks the designer to paste or attach it. Raw internal conversations and attachments remain working context and are not committed or copied into PRs by default.

Media inspection is capability-based. A model with reliable native support consumes the original video, recording, audio, or image directly. Otherwise vstack creates a lightweight local evidence pack with useful frames, transcript when relevant, metadata, and the original source reference. In either case, the next stable output is a concise confirmation of the problem vstack believes the evidence shows.

## End-to-end workflow

```text
Designer creates isolated effort in known repository
  -> selects vstack Kilo agent
  -> supplies prompt, pasted content, media, links, or files
  -> vstack normalizes the request
  -> reads repo guidance and applicable kilo-design authority
  -> inspects the current experience and traces relevant implementation
  -> separates observations from hypotheses and agrees on the problem or exploration question
  -> identifies the smallest coherent scope and adjacent drift
  -> maps the meaningful solution space
  -> uses parallel Kilo subagents only when useful
  -> creates exploratory artifacts when they resolve uncertainty
  -> returns compact direction checkpoint
  -> designer steers or chooses a direction
  -> vstack implements or prepares the chosen artifact
  -> designer reviews an early live result before secondary prototype flows are expanded
  -> vstack responds and polishes iteratively
  -> designer accepts the completed effort
  -> effort becomes Ready to publish or Ready to deliver
  -> designer triggers publication when needed
  -> vstack prepares the final requester reply
  -> optional kilo-design learning suggestion
```

## Direction checkpoint

For vague requests, the first meaningful return is a short problem-framing conversation. Inspect enough of the experience to distinguish stated intent, observations, and hypotheses. Help the designer establish what should improve or what an exploration should answer. The designer may lack the brief too. Do not replace that conversation with solution choices. Clear, already scoped requests can proceed directly.

After framing is agreed, the direction checkpoint is a compact summary containing:

1. The problem vstack believes it is solving.
2. The relevant routes, components, code, and current behavior it found.
3. The proposed scope and separately identified adjacent drift.
4. The meaningful solution directions and their real tradeoffs.
5. vstack's recommendation.
6. One focused question or decision when designer judgment is required.

Detailed code traces, screenshots, and prototypes stay linked or expandable. The checkpoint is not a report-writing exercise.

## Exploration policy

Present only meaningfully different directions needed for the decision; there is no default option quota.

Exploration is complete when:

- Important decision axes are named.
- Plausible solution regions are represented.
- Remaining alternatives are cosmetic variations.
- Serious directions expose their user, product, and implementation tradeoffs.
- The recommended direction resolves the problem elegantly and coherently.

The primary vstack agent works alone on narrow tasks. It may spawn independent Kilo subagents for broad, novel, high-impact, or clearly separable exploration. The primary agent synthesizes their work and remains the designer's single point of contact.

Prototypes are conditional. Copy work may need no visual artifact; a small UI adjustment may use Storybook; a redesign may need a fuller interaction prototype.

Present the first visual as soon as the agreed question can be judged. Approval of a written direction does not approve its visual execution. Add secondary flows and simulations only when needed for the next design decision. Distinguish ready for visual feedback from ready for delivery, and follow mandatory repository checks at the applicable stage.

## Design authority and native fit

vstack treats `kilo-design` as cross-repository authority rather than an implementation destination.

That authority is maturity-aware. Finalized tokens and generated product artifacts are used wherever applicable. A functioning product skill is loaded only for the surfaces it currently supports. When no functioning skill exists, vstack grounds the work in shipped product components and host-native conventions, then reports the missing design guidance as a coverage gap without blocking the effort.

Before delivery, it verifies that the result belongs in the target Kilo product:

- Canonical tokens and semantic roles are followed.
- Existing primitives and host-native behaviors are reused appropriately.
- Shipped Kilo examples inform patterns and density.
- Voice, product nouns, hierarchy, and interaction behavior fit the surface.
- Required states, accessibility, responsiveness, and keyboard behavior are covered when relevant.
- Deliberate deviations are named.
- Adjacent inconsistency is surfaced without silently expanding scope.

## Artifact and polish loop

Design review happens through the closest observable experience:

- Real browser route.
- Storybook story.
- IDE extension development host.
- CLI session.
- Static or interactive prototype.
- Another task-appropriate runtime.

The loop is:

```text
Build or update artifact
  -> designer experiences it
  -> designer points, annotates, tunes, or explains
  -> vstack updates the artifact
  -> affected behavior and native fit are verified
  -> repeat until designer acceptance
```

Orca Design Mode is the default direct element-to-agent path in Orca. Agentation is optional when persistent annotation queues, two-way threads, or cross-session lifecycle state are useful. DialKit is optional when live parameter tuning helps find the right value.

Designer acceptance, not annotation count or test completion alone, ends the polish effort.

## Autonomy boundaries

Before designer direction, vstack may:

- Read repository and supplied request context.
- Inspect the running product.
- Trace routes, components, behavior, and constraints.
- Create reversible prototypes, Storybook variations, and exploratory code.
- Use conditional Kilo subagents for solution coverage.

The designer owns:

- Consequential product framing and direction.
- Material scope expansion.
- Whether the next artifact is exploratory or production-oriented when ambiguous.
- Final polish acceptance.
- Publishing authorization.
- Whether reusable learning enters `kilo-design`.

## Delivery

Delivery is intentionally lightweight:

- Finished artifact, implementation, or PR.
- Brief notes and enough context to orient the recipient.

Rationale documents, specifications, state inventories, acceptance criteria, and implementation plans are produced only when requested or necessary to avoid consequential ambiguity.

Accepted code enters **Ready to publish**. It is not pushed automatically.

- In Orca, the designer uses the native Source Control and hosted-review action.
- In a terminal, the designer invokes an explicit publish action inside the active Kilo session. vstack previews the changes, validation, remote, base branch, and proposed PR before the authorized push and PR creation.

Publication prepares commit and PR details, then prepares a final Slack or requester reply with the resulting link. The designer reviews and sends the reply.

## Optional learning

When an effort reveals a reusable pattern, authority clarification, canonical example, or durable design lesson, vstack may briefly suggest capturing it in `kilo-design`.

The designer may capture it now, leave it manual for later, or ignore it. vstack never writes to `kilo-design` automatically and does not create a learning task when nothing meaningful was learned.

## Explicit MVP exclusions

- Authenticated Slack retrieval or proactive mention discovery.
- Okta or browser-session automation.
- A standalone vstack dashboard or inbox.
- A central coordinator agent or manager-of-managers.
- Codex, Claude Code, Super, or other agent integrations.
- Hosts beyond Orca and a regular terminal.
- Automatic writes to `kilo-design`.
- Automatic pushes, PRs, or final requester messages.

## MVP acceptance criteria

The MVP is successful when the designer can:

1. Create an isolated effort in a known Kilo repository.
2. Select the vstack Kilo agent and provide an informal or multimodal request.
3. Receive a grounded direction checkpoint without explaining the workflow manually.
4. Compare materially different solutions with adequate coverage.
5. Review and steer a real artifact through repeated polish passes.
6. Receive a result that fits the target Kilo product rather than generic generated UI.
7. Accept the effort and deliberately publish or deliver it with minimal packaging.
8. Repeat the process on copy, a small UI change, and a larger experience redesign without changing workflows.

## Remaining implementation decisions

These do not change the product boundary:

- Exact Kilo file paths and safe update or conflict behavior for the repository setup command.
- How vstack reliably detects the applicable generated token artifact and any functioning path-scoped product skill in the target repository.
- How the setup command detects native media capability and which local fallback tools it validates.
- The exact Kilo workflow-command syntax and final name for the in-session publishing action.
- Selection and privacy-safe capture of the first real copy, UI-polish, and redesign evaluation tasks from the designer's active workload.
