# ADR 0002: Use progressive autonomy with designer checkpoints

Status: accepted

## Context

The designer wants vstack to discover relevant Slack mentions and begin work without waiting for a manual prompt. The designer must also be able to invoke it directly for any experience worth improving. In either case, vague intent does not contain enough product context for an agent to choose a final direction safely.

Making the designer initiate every workflow preserves the current bottleneck. Allowing the agent to design and ship without checkpoints removes the judgment the system is meant to amplify.

## Decision

vstack is agent-operated and designer-supervised.

The agent may autonomously perform reversible preparation:

- Detect and triage candidate design requests.
- Read authorized conversational context and attachments.
- Map likely product surfaces and workspaces.
- Explore relevant codebases.
- Locate the current implementation and related work.
- Reconstruct the current experience.
- Identify ambiguity, missing context, constraints, and promising questions.
- Prepare an intake artifact and initial hypotheses.
- Create reversible exploratory artifacts such as Storybook variants, static routes, and prototypes.

The designer owns consequential judgment:

- Confirming or reframing the user problem.
- Supplying product context unavailable in the source material.
- Choosing between meaningfully different experience directions.
- Deciding when the result has reached the required level of polish.
- Selecting implementation versus developer-handoff delivery when the request does not establish it.

Before direction is established, exploratory code and artifacts are allowed. They must remain clearly separated from production commitment and easy to discard.

After direction is established, the agent may implement the selected direction and repeatedly return with visible, testable progress. A checkpoint is a steering surface, not a request for the designer to redo the work.

## Consequences

- vstack needs both manual invocation and optional event-driven intake adapters.
- Slack detection must distinguish actionable requests from ordinary mentions.
- Automatic requester acknowledgment follows the target project's communication policy and may be overridden per request.
- Repository mapping must express confidence and preserve uncertainty.
- Exploratory local changes are allowed before designer direction; production changes, Slack replies, pushes, and PR creation remain separate actions.
- Review is iterative. “Polish” is a loop with evidence, not one final approval step.
- The designer should receive synthesized decisions and artifacts rather than raw agent logs.

## Unresolved permission boundary

Completion replies are prepared for designer review and are never sent automatically. Pushes and PR creation happen only through an explicit designer publishing action. Branch isolation and reversible exploratory code creation are explicitly allowed; whether Slack acknowledgment is automatic is configured per project, and automatic replies always use the vstack bot identity.
