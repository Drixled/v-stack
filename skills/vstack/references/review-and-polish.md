# Review and polish

The artifact is the review surface. Prose only orients the designer.

## Choose the closest observable artifact

Prefer, in order of usefulness for the actual decision:

- Real product route.
- Storybook or existing component harness.
- IDE extension development host.
- CLI session.
- Focused static or interactive prototype.

For an early prototype, expose the primary scenario and only the states needed to judge the agreed design question. Return for visual feedback before expanding secondary flows. During later polish or production work, cover relevant loading, empty, error, disabled, responsive, keyboard, focus, and host-specific states.

## Paper

Treat Paper as a UI canvas, not a presentation deck. For UI exploration, place clean product screens or flows on the canvas with only short artboard names needed to identify them. Keep rationale, recommendations, tradeoffs, evidence limits, and status in the conversation. Do not add headings, introductions, captions, callouts, or footers around the UI unless the designer explicitly asks for an annotated comparison or presentation board. Even then, use only the labels needed to compare the screens.

## Match verification to the stage

- **Ready for visual feedback:** confirm the artifact renders, the interaction under review works, and the review viewport is usable. State what is simulated or incomplete. Do not call this delivery-ready.
- **Ready for delivery:** run the applicable repository checks and verify affected behavior and native fit. Follow mandatory repository checks; prototype status does not override them.

Do not add a broad automated test suite just to validate a disposable layout. Add focused behavioral tests when the interaction being explored needs them, or repository rules require them. Run delivery checks at the required stage and repeat checks when changes or failures justify it. Passing tests cannot establish that the agreed problem was solved or that the designer likes the result.

## Orca

When Orca is available, use its browser and Design Mode for the shortest element-to-agent feedback loop. Before issuing Orca commands, load the installed `orca-cli` skill or the version-matched guide from `orca skills get orca-cli`; do not guess a changing CLI surface.

Use a concise worktree comment for phase visibility when useful: Discovering, Awaiting direction, Building artifact, Polishing, Ready to publish, or Blocked.

## Optional adapters

- Agentation is useful for persistent element annotations, threads, and cross-session feedback state.
- DialKit is useful for tuning a small number of meaningful design parameters.

Use either only when already available or explicitly requested. Do not install them, rebuild them, or turn every CSS value into a control.

## Loop

1. Open or update the artifact.
2. Tell the designer what changed and which states deserve attention.
3. Consume direct feedback, annotations, tuning, or questions.
4. Update the artifact and verify affected behavior and native fit.
5. Repeat until the designer explicitly accepts the result.

Annotation completion and passing tests are evidence, not acceptance.
