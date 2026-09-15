# Delivery

Designer acceptance moves the effort out of polish. It does not authorize publication.

## Choose the deliverable

- Production implementation: prepare a clean diff, validation evidence, commit and PR context.
- Prototype or developer handoff: provide the artifact, launch instructions, and only the notes needed to remove consequential ambiguity.
- Copy or tiny UX adjustment: provide the finished change and brief context; do not generate a design document by default.

Do not automatically create rationale documents, specifications, state inventories, acceptance criteria, or implementation plans unless requested or necessary for safe handoff.

## Ready states

- **Ready to deliver:** the artifact or notes are accepted and need no repository publication.
- **Ready to publish:** code is accepted and awaits explicit push and PR authorization.
- **Publishing:** an authorized publication action is running.
- **Published:** the PR exists and its link is known.
- **Failed:** publication stopped safely; the branch and prepared context remain recoverable.

In Orca, prepare the context and use the native Source Control publishing flow. In a regular Kilo session, `/vstack-publish` owns the preview, confirmation, idempotency check, push, and PR creation.

After publication, draft the requester reply with the result link. Never send it automatically.

Suggest a Kilo Design learning only when it is genuinely reusable. The designer decides whether and when to capture it.

