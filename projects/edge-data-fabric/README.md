# SEP Edge Data Fabric

Artifact Type: SHARED INFRASTRUCTURE / DATA-FABRIC CANDIDATE

Project Status: ARCHITECTURE

Maturity Status: DESIGN / INVENTORY-REPORTED

Public Repository Status: REFERENCE PROFILE

## System Role

SEP Edge Data Fabric is a historical data-fabric design candidate associated with the wider sovereign infrastructure and edge architecture.

It is not the same thing as Sovereign Mesh, Observatory, or ERICA Library:

- Sovereign Mesh concerns connectivity, identity-aware access, and constrained network paths.
- Observatory concerns telemetry ingestion, state construction, and failure-detection signals.
- ERICA Library concerns source identity, durable knowledge objects, extraction, provenance, and retrieval.
- Edge Data Fabric would need an explicit contract for how selected data/events move between edge producers and authorized consumers.

## Historical Disposition

The 2026-11-13 implementation disposition matrix classified SEP Edge Data Fabric as REFERENCE because its data-fabric design had not been validated.

The next gate was a field, retention, and trust-contract review. No data-plane runtime, production connector, schema, or measured throughput is claimed here.

## Required Architecture Questions

- Which edge nodes and producers are authoritative for each data class?
- Which events are telemetry, operational state, evidence, or derived knowledge?
- What are the delivery semantics, buffering, retention, and deletion rules?
- How are source identity, timestamps, quality, and provenance preserved?
- Which network zones and principals may publish, subscribe, or export?
- How are stale, duplicate, reordered, malformed, and missing events handled?
- What happens during partition, storage exhaustion, clock drift, and recovery?

## Non-Duplication Rules

Do not merge Edge Data Fabric into Sovereign Mesh as if data transport and network identity were the same responsibility. Do not make Observatory the source of truth for physical controller state. Do not create a competing Library object store.

## Next Verification Gate

Produce a versioned data/event contract and ownership matrix, then compare it with the existing SEP L0-L6 contracts and the private ERICA interfaces before any implementation is admitted.
