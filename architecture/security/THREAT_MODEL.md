# Threat Model

Artifact Type: SPEC
Maturity Status: DESIGN

This document enumerates assets, actors, boundaries, and attack surfaces for design purposes. No vulnerabilities are claimed as demonstrated; no penetration testing or security assessment has been performed in this repository. All entries are analytical/conceptual unless marked otherwise.

## Assets

| Asset | Description |
|---|---|
| Deterministic Control state | L1 FSM state and control parameters |
| Policy definitions | Rules governing Command authorization |
| Command/audit log | Record of all Commands and decisions |
| Telemetry streams | All telemetry classes per CPS_CONTROL_LOOP.md |
| Knowledge store | L4 data/knowledge artifacts |
| Network credentials | Mesh/identity keys for L3 connectivity |
| AI/Agent session state | L5 planning and intent data |

## Actors

| Actor | Trust Level |
|---|---|
| Human operator | Trusted, subject to authentication |
| AI/Agent | Untrusted for Execution; trusted only for recommendation within its sandbox |
| External network peer | Untrusted by default |
| Edge node (L2) | Trusted within its own segment; verified via network identity |
| Physical intruder | Untrusted, out of scope for software-only controls |

## Trust Boundaries

| Boundary | Between | Notes |
|---|---|---|
| Physical boundary | L0 <-> L1 | Physical access control is out of scope for this document. |
| Deterministic boundary | L1/L2 <-> L3-L5 | No Command from outside this boundary may reach Actuation without the AI Authority Contract. |
| Network boundary | L3 mesh <-> external networks | Segmentation and identity-based access apply. |
| Advisory boundary | L4-L5 <-> L1 | Knowledge/Intelligence layers are advisory only; see LAYER_CONTRACTS.md. |

## Attack Surfaces (Analytical)

| Surface | Concern | Status |
|---|---|---|
| Command submission path | Unauthorized or malformed Command reaching Policy Validation | CONCEPT — no implementation exists to assess |
| Telemetry ingestion | Spoofed or replayed telemetry affecting State Estimation | CONCEPT |
| Policy Engine | Policy bypass or misconfiguration | CONCEPT — Policy Engine not implemented |
| Network mesh | Lateral movement between edge nodes | CONCEPT — see projects/sovereign-mesh |
| Knowledge store | Poisoned or tampered knowledge influencing L5 recommendations | CONCEPT |
| AI prompt/tool interface | Prompt injection leading to unsafe recommended Commands | CONCEPT — mitigated only by design-level Policy Validation requirement |

## Identity and Privilege Domains

- Human identity domain: authentication mechanism [UNRESOLVED_SPEC: Requires Hardware/Code Verification].
- AI/Agent identity domain: session-scoped identifiers; no persistent credential model defined yet.
- Node identity domain (L2/L3): key-based identity per sovereign mesh concept; concrete key management [UNRESOLVED_SPEC: Requires Hardware/Code Verification].

## Secrets

- No secrets are stored in this repository.
- Secret handling requirements are stated as policy in [/memories/repo/workflow_rules.md-equivalent conventions]: environment-variable only, never in code or committed files. This is a requirement, not evidence of an implemented secrets manager.

## Telemetry, Command, Evidence, and Recovery Integrity

| Integrity Concern | Current Mitigation | Status |
|---|---|---|
| Telemetry integrity | Provenance field defined in telemetry.schema.json | DESIGN only, unenforced |
| Command integrity | policyDecision + audit event fields in command.schema.json | DESIGN only, unenforced |
| Evidence integrity | provenance field in evidence.schema.json | DESIGN only, unenforced |
| Recovery integrity | recovery-event.schema.json defines traceable fields | DESIGN only, unenforced |

## Explicit Non-Claims

This threat model does not claim:

- any vulnerability has been found,
- any mitigation has been implemented or tested,
- any penetration test, audit, or certification has occurred.

All such claims require future EXPERIMENT/MEASURED/VERIFIED evidence per [architecture/evidence/EVIDENCE_MODEL.md](../evidence/EVIDENCE_MODEL.md).
