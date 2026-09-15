# vstack

Status: MVP defined

vstack is a proposed operating system for AI-assisted product design and design engineering.

It is being designed from first principles, using gstack and pstack as reference architectures rather than adoption targets.

## Current product boundary

vstack should turn design intent from any source into a grounded design-engineering outcome. It must connect that intent to the correct Kilo surface and workspace, load the applicable `kilo-design` authority, understand the existing implementation, cover the solution space, conditionally prototype, select a native and elegant direction, implement or hand off, verify the real experience, and produce a PR-ready result.

The first workflow is based on the current work of Kilo's sole product designer. vstack may begin from a discovered request or a direct designer instruction. It should be agent-operated and designer-supervised: the agent resolves surfaces and workspaces, prepares grounded alternatives, and asks the designer for judgment at consequential product and design forks.

## Working questions

1. Who is the first user?
2. What real task should vstack own end to end?
3. What outcome makes that task complete?
4. Which decisions belong to the human, and which can the system make?
5. What durable artifacts should pass between stages?
6. What evidence proves the resulting experience is good?

## Documents

- [MVP specification](./mvp-spec.md)
- [Current workflow](./current-workflow.md)
- [Domain model](./domain-model.md)
- [Case 001: Agent manager modal request](./cases/001-agent-manager-modal.md)
- [Direction checkpoint template](./artifacts/direction-checkpoint.md)
- [Polish checkpoint template](./artifacts/polish-checkpoint.md)
- [Review adapter contract](./adapters/review-feedback.md)
- [Glossary](./glossary.md)
- [ADR 0001: Treat vstack as an operating system](./decisions/0001-operating-system-not-skill-pack.md)
- [ADR 0002: Use progressive autonomy](./decisions/0002-progressive-autonomy.md)
- [ADR 0003: Resolve the surface before designing](./decisions/0003-surface-resolution-first.md)
- [ADR 0004: Use coverage, not an option quota](./decisions/0004-solution-space-coverage.md)
- [ADR 0005: Treat kilo-design as design authority](./decisions/0005-kilo-design-authority.md)
- [ADR 0006: Keep scope under designer control](./decisions/0006-designer-controlled-scope.md)
- [ADR 0007: Use compact direction checkpoints](./decisions/0007-compact-direction-checkpoint.md)
- [ADR 0008: Review the experience through an artifact](./decisions/0008-artifact-first-polish.md)
- [ADR 0009: Integrate review tools through adapters](./decisions/0009-review-tool-adapters.md)
- [ADR 0010: Designer acceptance triggers delivery](./decisions/0010-acceptance-triggers-delivery.md)
- [ADR 0011: Delivery is lightweight by default](./decisions/0011-lightweight-delivery.md)
- [ADR 0012: Start as a central Kilo-aware system](./decisions/0012-central-kilo-system.md)
- [ADR 0013: Isolate every effort in a worktree](./decisions/0013-isolated-worktree-per-effort.md)
- [ADR 0014: Configure requester communication by project](./decisions/0014-project-communication-policy.md)
- [ADR 0015: Publish through an explicit action](./decisions/0015-explicit-publish-action.md)
- [ADR 0016: Separate repository and minimal MVP](./decisions/0016-separate-repo-minimal-mvp.md)
- [ADR 0017: Kilo executes vstack and Orca is the primary host](./decisions/0017-orca-host-kilo-agent.md)
- [ADR 0018: Start directly in the selected repository](./decisions/0018-direct-repo-entry.md)
- [ADR 0019: Use content-first multimodal intake](./decisions/0019-content-first-intake.md)
- [ADR 0020: Make design-system learning conditional](./decisions/0020-conditional-design-learning.md)
- [ADR 0021: Enter through a dedicated Kilo agent](./decisions/0021-dedicated-kilo-agent.md)
- [ADR 0022: Scale exploration with conditional subagents](./decisions/0022-conditional-exploration-subagents.md)
- [ADR 0023: Install vstack through a repository setup command](./decisions/0023-repository-setup-command.md)
- [ADR 0024: Consume Kilo Design according to surface maturity](./decisions/0024-maturity-aware-design-authority.md)
- [ADR 0025: Inspect media according to model capability](./decisions/0025-capability-based-media-intake.md)
- [ADR 0026: Publish from an explicit action inside the Kilo session](./decisions/0026-kilo-session-publish-trigger.md)
- [ADR 0027: Validate the MVP through real Kilo work](./decisions/0027-real-work-evaluation.md)
- [ADR 0028: Frame vague requests before selecting a direction](./decisions/0028-problem-framing-before-direction.md)
- [ADR 0029: Request-first startup and explicit Orca handoff (proposed)](./decisions/0029-request-first-startup.md)
