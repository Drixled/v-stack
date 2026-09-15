# Kilo product profile

Use this profile only for Kilo product work. The designer starts vstack inside the repository they believe owns the request. Treat that repository as authoritative unless evidence clearly conflicts.

## Repository families

Read [surfaces.yaml](surfaces.yaml) as a stable routing hint, then verify the live repository. Names and folder hints can drift; code search and repository instructions win.

- `kilo-cloud`: Kilo's web application and related web product surfaces.
- `kilo-landing`: Kilo's marketing and landing experience.
- `kilo-code`: editor extensions, JetBrains, CLI, browser extension, console, and other developer-tool surfaces contained by the core repository.
- `kilo-design`: canonical tokens and agent-facing design guidance. It is design authority, not the normal product implementation destination.

If the request clearly belongs to a different repository, stop before editing and ask the designer which codebase to use. Do not open another agent or worktree yourself in the MVP.

## Design authority

Read [design-authority.md](design-authority.md) before proposing or reviewing a product direction.

## Native product evidence

For every surface, inspect the current product repository for:

- Existing primitives and shared component libraries.
- A shipped component or route solving the closest comparable problem.
- Product nouns, information density, hierarchy, navigation, state handling, and host behavior.
- Storybook stories, visual tests, development hosts, or launch commands that expose the behavior.
- Existing drift that should be reported but not silently absorbed into scope.

Do not use the Kilo Design playground as canonical product UI.

