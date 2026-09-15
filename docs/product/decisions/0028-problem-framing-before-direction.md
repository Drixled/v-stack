# ADR 0028: Frame vague requests before selecting a direction

Status: accepted and implemented in workflow guidance

## Context

The first Agent Manager evaluation began with a screenshot and a vague request for a new design. The agent inferred a hierarchy problem, presented solution directions, then built an extensive prototype after the designer selected one. The designer still lacked a clear brief. Selecting a proposed solution had concealed the unresolved problem.

## Decision

For vague requests, vstack performs bounded discovery and a short problem-framing conversation before solution selection. It separates requester intent, observed issues, and hypotheses. The designer may not know the answer; the agent helps investigate, draft a requester question, agree on behavior-preserving polish, or define an exploratory question.

An already clear brief does not need another checkpoint. Once framing is agreed, the existing direction checkpoint applies. A written direction authorizes an initial visual for feedback, not approval of its visual execution.

Prototypes reach the designer as soon as the agreed design question can be judged. Secondary flows and simulations are conditional. Verification distinguishes an early artifact for feedback from a deliverable, while preserving mandatory product repository checks.

## Evaluation

Follow-up real runs showed that the agent could acknowledge uncertainty yet still recommend polish or ask for redesign depth before establishing intent. After direct correction, it produced a useful assessment and requester clarification without editing files. The workflow now puts the trigger question before scope options and distinguishes UI facts from design judgments and implementation concerns.

Evaluate the quality of judgment in normal use, not exact wording or a fixed question sequence. The criterion is whether the agent helps develop the brief without the designer first having to reject an assumed solution. Do not require repeated fresh worktrees solely to reproduce a scripted answer.

During the next real vague request after the package update is installed, observe whether the first meaningful return helps clarify the problem instead of selecting a layout. If the designer lacks context, check that the agent recommends useful investigation without inventing user needs or blocking on a complete brief.

Then agree on visual polish or a named exploration and verify that the first visual appears before unnecessary simulation and delivery validation work. Also use a real narrow copy request to check that the new guidance does not add needless questions.

Package checks validate distribution and helpers. They do not establish these behavioral outcomes; a real Kilo run is still needed.
