# ADR 0001: Treat vstack as an operating system, not a skill pack

Status: proposed

## Context

gstack demonstrates an end-to-end lifecycle composed of specialist skills and supporting runtime tools. pstack demonstrates a behavioral system composed of principles, playbooks, routing, and model-aware delegation.

vstack is intended for product design and design engineering. Copying either command surface would produce another broad collection without establishing a distinct product model.

## Decision

Design vstack as a coherent operating system with four initial layers:

1. Principles that govern product and implementation judgment.
2. Workflows that handle recognizable jobs.
3. Artifacts that preserve decisions between stages.
4. Evidence that verifies the resulting experience.

Skills and commands are delivery mechanisms, not the core architecture.

## Consequences

- The first workflow must be defined before the complete command surface.
- Each stage must have explicit inputs, outputs, and completion criteria.
- New skills must earn their place by supporting a workflow or enforcing a principle.
- Product quality must be demonstrated through evidence, not persona-based review alone.

## Open issue

The first user and first end-to-end job have not been selected. This decision remains proposed until that boundary is clear.
