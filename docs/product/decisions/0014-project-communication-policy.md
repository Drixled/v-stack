# ADR 0014: Configure requester communication by project

Status: accepted

## Context

When vstack discovers a request through Slack, automatically acknowledging it can reassure the requester that work has started. In other projects, a reply may create an unwanted commitment, expose premature work, or add noise. One global rule cannot represent both contexts.

## Decision

Requester communication is configured per project or product adapter.

Each adapter can default to:

- Automatically acknowledge an accepted request.
- Remain silent until the designer reviews the effort.

The designer can override the default for an individual request.

Reading and beginning internal work does not inherently authorize an external reply. The configured communication policy supplies that authorization.

All automatic Slack communication is posted by an explicitly identified vstack bot. vstack does not post through the designer's identity or impersonate the designer's voice.

After the designer accepts the finished work, vstack prepares a completion reply with the relevant artifact or PR. It does not post that completion reply automatically. The designer reviews and sends it.

## Consequences

- vstack can behave differently across Kilo projects without changing its core workflow.
- Projects with established request channels can receive immediate acknowledgment.
- Sensitive or ambiguous work can remain private until reviewed.
- Outbound communication state belongs in the product adapter alongside repository and runtime context.
- Requesters can distinguish automated workflow updates from messages written by the designer.
- Final delivery communication remains under designer control even when intake acknowledgment is automated.
