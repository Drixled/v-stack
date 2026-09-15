# Case 001: Agent manager modal request

Status: source case

## Signal

A teammate mentions the designer in Slack and asks for “a new design” because an agent manager modal “has potential to improve.” The message includes a screenshot of a New Worktree modal but does not identify the user problem, desired outcome, urgency, affected repository, or acceptance criteria.

## Ambiguity exposed by the thread

The designer initially connects the request to an earlier multi-agent or Ultramode discussion from another teammate. The requester clarifies that this is instead the New Worktree modal.

This demonstrates that a design request may overlap with nearby initiatives while referring to a different surface or interaction. vstack must reconstruct related context without silently merging distinct problems.

## What vstack should do

1. Accept the supplied Slack screenshot or pasted request as input.
2. Inspect supplied context and attachments. Do not require direct Slack access.
3. Extract the named interface, visible UI, requester, related initiatives, and missing information.
4. Distinguish the New Worktree modal from the multi-agent or Ultramode concept.
5. Establish the owning product surface in the selected repository. Automatic discovery across known repositories is the proposed startup change in ADR 0029.
6. Locate the modal, trace its current behavior, identify components and constraints, and find related work through read-only discovery.
7. Load the applicable `kilo-design` product adapter, tokens, recipes, and canonical examples.
8. Explain that the request identifies a modal but does not establish what needs improving. Separate observed issues from hypotheses such as task hierarchy.
9. Ask for missing context that affects scope. If the designer does not know, recommend a focused investigation or requester question; do not require a complete brief.
10. Agree on the problem, behavior-preserving polish scope, or exploratory question before presenting design directions.
11. Return an early visual after direction selection, then iterate through designer feedback before expanding secondary interactions.
12. Finish as a verified implementation and draft PR, or as a developer-ready change contract and deliverable.

## Proposed intake artifact

```text
Request: Improve the New Worktree modal
Requester: Marius
Source: Slack mention and attached screenshot
Surface: unresolved until repository mapping is confirmed
Related context: separate multi-agent / Ultramode discussion
Current evidence: screenshot plus located runtime implementation
Problem: not yet established
Constraints: not yet established
Open product questions: concise list after discovery
Recommended next step: direction review with the designer
```

## Design lesson

Slack is a signal source, not the source of truth. vstack must convert conversational fragments into a grounded work item while preserving uncertainty and provenance.
