# ADR 0029: Request-first startup and explicit Orca handoff

Status: proposed implementation; current launcher still uses direct repository entry

## Problem

ADR 0018 assumes the designer knows the owning repository before starting. The real evaluation showed that discovering the owner is part of the work the designer wants vstack to handle. Creating an Orca worktree from an external Kilo session also left history in the package repository while files and previews lived elsewhere.

## Proposed behavior

1. Accept the original request from the entry session, even outside a product repository.
2. Search an explicit set of known product repositories read-only. Use screenshot labels, terminology, routes, and component evidence to identify the owning surface. Ask only when ownership remains ambiguous.
3. Once the target and isolation scope are established, create and activate an Orca worktree and launch Kilo with the vstack agent there, using the installed Orca CLI guide.
4. Transfer the original request and attachments, confirmed observations, unresolved questions, and any designer decisions. The receiving session starts in the product worktree and loads its instructions.
5. Verify that the receiving session is ready, identify it to the designer, and stop the entry session's work. Keep one active owner of the design effort.

Keep the terminal fallback explicit when Orca is unavailable. Never silently create an invisible worktree and continue as though the conversation moved. Starting from an existing isolated product worktree should keep the direct path.

## Implementation checks still required

- Decide where the explicit local repository registry lives and how it is maintained.
- Verify Kilo startup with a custom agent in Orca and reliable delivery of text and attachments.
- Verify session continuation across directories before promising to move the same conversation. A fresh product session with explicit context transfer is an acceptable fallback.
- Handle a failed launch or handoff without duplicate sessions or lost context.

This proposal does not change the current launcher or authorize a live installation. ADR 0018 remains the supported startup path until the handoff is implemented and verified. vstack remains an agent and skill package, with no dashboard or permanent coordinator.
