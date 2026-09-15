# ADR 0019: Use content-first multimodal intake

Status: accepted

## Context

Many requests originate in a managed Kilo Slack workspace protected by Okta. A Slack permalink does not guarantee that Kilo or vstack can authenticate, read the channel, access the thread, or download its attachments. Making authenticated Slack retrieval an MVP dependency would introduce enterprise OAuth, permissions, admin approval, session handling, and privacy work before the design workflow can be tested.

Requests also originate outside Slack and may arrive as a spontaneous prompt, pasted text, screenshot, screen recording, video, file, or web link.

## Decision

vstack intake is content-first and multimodal. The designer can begin with any useful combination of:

- A freeform prompt.
- Copied Slack message or thread text.
- Images or screenshots.
- A screen recording or video.
- Local files.
- Web links.
- An optional Slack permalink.

A Slack permalink is treated as provenance and a backlink unless the active environment already has authorized Slack access. vstack never assumes it can fetch the message.

If a link is inaccessible and the supplied content is insufficient, vstack asks the designer to paste the relevant text or attach the evidence. It does not attempt to bypass Okta, copy browser credentials, scrape an authenticated session, or make Slack login part of the workflow.

vstack normalizes the supplied material into a small internal request context containing the interpreted problem, relevant evidence, and source references. It then returns the normal compact confirmation checkpoint.

Raw internal conversations and attachments are working context. They are not committed to the product repository or copied into a PR by default.

## Future Slack integration

If automatic Slack intake becomes valuable, it should use an organization-approved Slack app with explicit OAuth scopes and channel access. It should feed the same content-first intake contract rather than creating a second workflow.

## Consequences

- The MVP works on the managed laptop without solving Okta authentication.
- Slack-originated and self-initiated work use the same entry point.
- The designer can supply the fastest available evidence instead of completing a form.
- Source links remain useful even when vstack cannot open them.
- Sensitive internal context stays out of product history unless deliberately included.
- Text, image, and video handling can improve independently behind the same intake contract.
