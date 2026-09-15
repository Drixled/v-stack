# ADR 0023: Install vstack through a repository setup command

Status: accepted

## Context

The first vstack release is primarily for one designer, but a completely manual installation would make the local machine an undocumented source of truth. A formal Kilo plugin would add packaging, compatibility, and release work before the workflow has been validated through real design efforts.

## Decision

The vstack repository provides a small setup command that installs or updates the complete Kilo workflow package.

The setup command should:

- Install or update the dedicated `vstack` custom agent.
- Install its primary skill, references, templates, and explicit workflow commands.
- Verify that vstack can discover the Kilo Design artifacts or functioning product skill already available to the target repository, without taking ownership of their installation or lifecycle.
- Validate required paths and tools, while treating review integrations as optional.
- Detect local modifications before replacing managed files.
- Provide a corresponding uninstall or clean removal path.

The repository remains the versioned source of truth. The MVP does not require a marketplace listing or formal Kilo plugin package.

## Consequences

- Installation remains minimal but reproducible.
- Agent, skill, references, and commands update together.
- vstack can later become a formal package without changing the working model.
- The installer must define safe update, conflict, and removal behavior.
- Exact Kilo file paths remain an implementation detail to verify during scaffolding.
