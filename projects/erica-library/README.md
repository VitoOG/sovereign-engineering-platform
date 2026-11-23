# ERICA Library — Knowledge and Evidence Subsystem

Artifact Type: ERICA OS SUBSYSTEM PROFILE

Project Status: MIXED MATURITY

Maturity Status: MIXED (current Go library slice historically locally tested; historical Python candidates remain unverified)

Public Repository Status: ARCHITECTURE / PROVENANCE SUMMARY — no Library runtime source is published here

## System Role

ERICA Library is the knowledge, source, extraction, provenance, and evidence subsystem associated with ERICA OS.

This profile records one subsystem lineage. It does **not** create a second platform, competing document application, or independent authoritative database.

The intended pipeline is:

`SOURCE REGISTRY → READ-ONLY COLLECTION → ORIGINAL OBJECT PRESERVATION → FORMAT-AWARE EXTRACTION / SHREDDER → SQLITE METADATA + FTS5 → EVIDENCE REVIEW → APPROVED KNOWLEDGE / RETRIEVAL`

## Related Generations and Components

| Name | Role | Historical disposition / maturity boundary |
|---|---|---|
| Smart Library | Earlier knowledge/library implementation candidate | ADAPT was the provisional 2026-11-13 disposition; source behaviour, schema, and security require comparison |
| ERICA Library v1 | Knowledge subsystem specification and target architecture | Specification exists; it is not proof that every stage is deployed |
| Shredder | Format-aware extraction and typed-block processing component | Reuse the existing Go Library/object-store/SQLite substrate; first slice is bounded/read-only; later adapters remain staged |
| Knowledge Forge | Downstream consolidation/cataloguing candidate | Observed implementation consumes an existing ingestion output directory; it is not the raw-source collector |
| Knowledge Graph | Relationship and traceability layer | Target architecture; graph relationships must remain source-bound and reviewable |
| Knowledge Graph Navigator | Separate historical navigation/tooling candidate | See [projects/knowledge-graph-navigator](../knowledge-graph-navigator/README.md); do not assume it is the current graph runtime |

## Current Go Library Line

The 2026-11-13 ERICA functional-state report recorded a locally tested Go target slice with:

- Source registration and bounded text extraction.
- Content-addressed object storage.
- SQLite metadata and FTS5 search.
- Evidence and knowledge review states.
- HTTP APIs for source, ingestion, search, and project records.
- Durable workflow/task state and local backup/restore mechanisms in the wider Go target.

The report described this as a local/private implementation slice. The code is not included in this public SEP repository, so public reproducibility is not established. This is a dated historical status record, not a claim about the current live runtime.

## Architectural Rules

- Keep original source bytes distinct from extracted text, normalized records, AI-derived summaries, and approved knowledge.
- Preserve source identity, version, hashes, and stable locators through extraction and retrieval.
- Keep SQLite metadata authority separate from rebuildable FTS5 projections.
- The original object store remains the authoritative source-byte store in the Go Library design.
- AI output does not become authoritative merely because it is indexed.
- Review/approval is a state transition, not a synonym for verification.
- The public SEP repository documents contracts and evidence boundaries; it does not own ERICA OS runtime state.

## Integration and Non-Duplication

- The Go Library is a domain within ERICA OS, not a second database/application competing with ERICA.
- Shredder is an extraction processor that should use the existing Library storage and state contracts.
- Knowledge Forge is downstream of ingestion; do not collapse collection, extraction, consolidation, and graph construction into one opaque step.
- Knowledge Graph Navigator is a separate historical candidate and must pass schema/provenance comparison before reuse.
- Smart Library is not automatically the same code generation as ERICA Library v1 or the current Go Library.

## Next Verification Gates

1. Pin each Python/Go generation to an exact source root, revision, and source identity.
2. Compare schemas and provenance fields before adapting Smart Library.
3. Inspect and test the upstream ingestion dependency consumed by Knowledge Forge.
4. Validate Shredder processor contracts, archive/path safety, idempotency, cancellation, and output validation.
5. Verify end-to-end source → extraction → search → evidence review → approved knowledge.
6. Verify backup/restore independently.
7. Export a sanitized, reproducible subset before assigning PUBLIC-VERIFIED status.

No public deployment, complete knowledge graph, or end-to-end production pipeline is claimed.
