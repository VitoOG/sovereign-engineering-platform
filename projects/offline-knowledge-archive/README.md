# Offline Knowledge Archive — Digital Preservation

Artifact Type: DIGITAL PRESERVATION / KNOWLEDGE INFRASTRUCTURE PROJECT

Project Status: DESIGN / PREPARATION

Maturity Status: DESIGN — archive scope and acquisition/verification workflow are defined; a complete usable offline archive is not claimed

Public Repository Status: ARCHITECTURE SUMMARY ONLY

## System Role

The Offline Knowledge Archive is a preservation-oriented collection of technical, scientific, programming, and general reference material intended to remain usable without public internet access.

It is related to, but distinct from, ERICA Library:

- Offline Knowledge Archive preserves original distributable knowledge packages and their integrity metadata.
- ERICA Library registers, extracts, indexes, and relates local engineering sources.
- Shredder processes supported formats into typed, traceable content.
- Knowledge Graph represents relationships and derived assertions with source provenance.

The archive is not a second ERICA OS database.

## Scope

Intended content classes include:

- Offline encyclopedic and language-specific reference material.
- Programming and engineering knowledge collections.
- Scientific and technical reference packages.
- Selected educational resources and documentation.

ZIM is one of the intended offline distribution formats. Exact editions, language variants, package sizes, licence terms, and update cadence must be tracked in a versioned manifest.

## Preservation Pipeline

`SOURCE SELECTION → LICENCE / EDITION REVIEW → DOWNLOAD → CHECKSUM VERIFICATION → IMMUTABLE STORAGE → INDEX REGISTRATION → OFFLINE ACCESS TEST → PERIODIC INTEGRITY AUDIT`

## Maturity and Evidence Boundary

| Capability | State |
|---|---|
| Need for long-term offline knowledge preservation | ESTABLISHED PROJECT REQUIREMENT |
| Candidate archive categories and ZIM collections | INVENTORIED / PLANNED |
| Acquisition and checksum workflow | DESIGN |
| Kiwix-based access layer | NOT VERIFIED as installed or configured in the historical baseline |
| Complete archive acquisition | NOT VERIFIED |
| Integrity verification of all planned packages | NOT VERIFIED |
| Independent restore / access drill | NOT VERIFIED |

A package appearing in a plan or manifest is not evidence that it was downloaded, is intact, or can be opened offline.

## Integration Rules

- Preserve downloaded source objects and their checksums.
- Do not rewrite or silently replace source packages during indexing.
- Keep acquisition metadata, licence/edition, source URL, timestamp, size, and digest.
- Treat generated indexes as rebuildable derivatives.
- Keep ERICA Library metadata and FTS projections separate from the original archive objects.
- Record archive health and storage capacity before acquisition or migration.

## Next Verification Gates

1. Freeze a canonical acquisition manifest with editions, languages, licences, and expected sizes.
2. Verify downloads against authoritative checksums where available; otherwise compute and record local digests.
3. Record storage capacity and reserve before acquisition.
4. Validate each package with the intended offline reader.
5. Perform a disconnected access test.
6. Run a periodic hash audit and a restore/access drill.

No complete archive, full offline coverage, or verified preservation service is claimed.
