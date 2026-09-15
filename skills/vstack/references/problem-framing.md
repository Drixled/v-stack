# Problem framing

Use this when a request names a screen or asks for a new design without explaining what should improve. The goal is a shared brief, not a questionnaire or a formal document.

## Establish what is known

Inspect the supplied material and enough of the current implementation to identify the surface, behavior, constraints, and existing components. Separate:

- Requester intent actually stated in the input.
- Observable behavior or friction supported by evidence.
- Hypotheses about user difficulty, causes, and possible improvements.

A crowded screenshot can suggest hierarchy issues. It does not prove that hierarchy is the requester's concern or that users need a different flow. Finding the owning code does not establish the problem.

Describe concrete evidence separately from design judgment: “the name field precedes the prompt” is observable; “the hierarchy is confusing” is an assessment that needs support. Missing tests, custom CSS, and complex component code are implementation concerns, not evidence of user difficulty by themselves.

## Have the missing conversation

Briefly explain what the request does and does not tell us. Start with what prompted the request, rather than leading with your preferred diagnosis. For example: “Do we know what made the requester want to revisit this modal?” Use natural wording suited to the conversation, not a fixed script. Bring only the few observations that help decide what to clarify or investigate.

Do not ask the designer to choose between solutions to a problem you have just assumed. Do not request a full brief, metrics, or requester access as a prerequisite for useful discovery.

Questions such as “polish, regroup, or rethink the flow?” belong after framing. A recommended scope option can hide the missing brief even when the designer selects it. Do not use visual polish as the default answer to unknown intent; recommend it when appearance is an explicit objective or the designer deliberately chooses that limited scope after discussing the uncertainty.

If the designer does not know, recommend the smallest useful next step:

- Inspect the current experience and bring back concrete observations for discussion.
- Draft one focused clarification for the requester, without sending it.
- Agree on visual polish that preserves behavior when appearance is the objective.
- Agree on a limited exploration whose purpose is to answer a named uncertainty.

Present the best next step for the actual evidence; this is not a menu to show every time. Reuse context already supplied and do not repeat answered questions.

When drafting a requester clarification, ask about the trigger or a concrete example first. Do not make the requester classify their concern using your design terminology. Keep the assessment and next step short; uncertainty alone does not justify a long research report.

## Exit condition

Proceed when the designer and agent share an intended improvement and scope, or an explicit question for exploratory work. Capture that agreement briefly in the conversation. Keep assumptions visible and revisit framing if new evidence undermines it.

An explicit request such as “shorten this label without changing behavior” already establishes scope. Do not add a separate approval ceremony for it.
