# ADR 0025: Inspect media according to model capability

Status: accepted

## Context

Design requests may include screenshots, videos, screen recordings, and audio. Some models can inspect video directly; others need frames, transcripts, or metadata. Requiring preprocessing in every case adds latency and loses temporal context, while assuming native video support makes the workflow unreliable across models and hosts.

## Decision

vstack chooses the smallest reliable media-inspection path supported by the active model and environment.

- If the active model can consume the supplied media directly and reliably, vstack uses the original attachment.
- Otherwise, vstack creates a lightweight local evidence pack containing useful key frames or a contact sheet, an audio transcript when relevant, duration and basic metadata, and a reference to the original source.
- vstack may still extract targeted frames or timestamps after native inspection when they make a finding easier to verify.
- Derived media, transcripts, and internal attachments remain temporary working context and are not committed by default.

Regardless of inspection path, vstack returns a concise problem confirmation before substantive exploration or implementation. It states what it believes is wrong, the evidence supporting that interpretation, and asks one focused question only when material ambiguity remains.

## Consequences

- Capable models preserve the full temporal evidence without unnecessary conversion.
- Less capable models receive a predictable, inspectable fallback.
- The workflow remains portable across model improvements and host differences.
- Media processing is implementation detail; problem confirmation is the stable product contract.
- The designer can correct a misunderstanding before vstack designs the wrong solution.
