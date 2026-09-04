# Competency Evidence Matrix

Artifact Type: MODEL
Maturity Status: DESIGN

Governed by [architecture/evidence/EVIDENCE_MODEL.md](architecture/evidence/EVIDENCE_MODEL.md). Confidence descriptors below reflect only what is actually present in this repository. Document existence alone justifies "Conceptual" or "Design-level" confidence at most; it never justifies "Implementation-backed", "Experiment-backed", "Measured", or "Verified" confidence.

Confidence vocabulary (mandatory, use exactly one per row):

- Conceptual — described in a document with rationale, no design detail.
- Design-level — a specific architecture/contract/schema exists with defined inputs/outputs/constraints.
- Implementation-backed — working code/configuration/hardware exists in this repository.
- Experiment-backed — an implementation has been executed under a repeatable procedure with recorded results.
- Measured — a quantified result exists with stated method and precision.
- Verified — a measured result has been independently reproduced or reviewed.

| Competency | Claim | Artifact Type | Maturity | Architectural Principle | Implementation | Test | Measurement | Evidence | Confidence |
|---|---|---|---|---|---|---|---|---|---|
| Systems Architecture | Multi-layer CPS architecture can be decomposed into deterministic layers with explicit contracts | SPEC | DESIGN | Separation of concerns and explicit state ownership | Not implemented | Not implemented | N/A | [architecture/LAYER_CONTRACTS.md](architecture/LAYER_CONTRACTS.md) | Design-level |
| Systems Engineering | Engineering loop supports iterative, evidence-gated improvement | SPEC | DESIGN | Observe -> Decide -> Verify -> Learn | Not implemented | Not implemented | N/A | [architecture/evolution/README.md](architecture/evolution/README.md) | Design-level |
| Cyber-Physical Engineering | Physical and digital loops are coupled via explicit state, telemetry, and a closed feedback path | SPEC | DESIGN | Closed-loop control with multi-stage telemetry | Not implemented | Not implemented | N/A | [architecture/cps/CPS_CONTROL_LOOP.md](architecture/cps/CPS_CONTROL_LOOP.md) | Design-level |
| Embedded | Deterministic local control is the sole authority for actuation | SPEC | DESIGN | Policy-gated authority, no bypass of L1 | Not implemented | Not implemented | N/A | [architecture/LAYER_CONTRACTS.md](architecture/LAYER_CONTRACTS.md#l1-embedded) | Design-level |
| Edge Computing | Local operation should continue during cloud/network outage | SPEC | CONCEPT | Offline-first | Not implemented | Not implemented | N/A | [docs/infrastructure/README.md](docs/infrastructure/README.md) | Conceptual |
| Linux | Linux-based supervision and isolation are a planned baseline | SPEC | CONCEPT | Recoverability and observability | Not implemented | Not implemented | N/A | [projects/arm64-workstation/README.md](projects/arm64-workstation/README.md) | Conceptual |
| Networking | Private mesh with constrained management paths is planned | SPEC | CONCEPT | Zero-trust segmentation | Not implemented | Not implemented | N/A | [projects/sovereign-mesh/README.md](projects/sovereign-mesh/README.md) | Conceptual |
| Cybersecurity | Security is treated as architecture with an explicit decision chain | SPEC | DESIGN | Identity -> AuthN -> AuthZ -> Policy -> Audit | Not implemented | Not implemented | N/A | [architecture/security/THREAT_MODEL.md](architecture/security/THREAT_MODEL.md) | Design-level |
| Distributed Systems | Edge nodes are intended to coordinate via explicit state/interface contracts | SPEC | CONCEPT | Deterministic interfaces | Not implemented | Not implemented | N/A | [architecture/network/README.md](architecture/network/README.md) | Conceptual |
| AI | AI is restricted to a recommendation/orchestration role with no direct actuation authority | SPEC | DESIGN | No uncontrolled LLM to actuator path | Not implemented | Not implemented | N/A | [architecture/security/AI_AUTHORITY_CONTRACT.md](architecture/security/AI_AUTHORITY_CONTRACT.md) | Design-level |
| RAG | Knowledge retrieval is intended to be provenance-tagged | SPEC | CONCEPT | Evidence-first reasoning | Not implemented | Not implemented | N/A | [architecture/knowledge/README.md](architecture/knowledge/README.md) | Conceptual |
| Agents | Capability-first execution with mandatory policy checks | SPEC | DESIGN | Capability Resolution -> Policy Validation | Not implemented | Not implemented | N/A | [docs/ai/CAPABILITY_SYSTEM.md](docs/ai/CAPABILITY_SYSTEM.md), [architecture/security/AI_AUTHORITY_CONTRACT.md](architecture/security/AI_AUTHORITY_CONTRACT.md) | Design-level |
| Automation | Workflows are designed to be deterministic and recoverable | SPEC | DESIGN | Detect -> Isolate -> Degrade -> Recover -> Verify | Not implemented | Not implemented | N/A | [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md) | Design-level |
| Reliability | Degraded operation and recovery are designed as first-class states | SPEC | DESIGN | Failure-first engineering | Not implemented | Not implemented | N/A | [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md) | Design-level |
| Observability | Observability is designed to construct explicit system state from multi-class telemetry | SPEC | DESIGN | Telemetry as state input | Not implemented | Not implemented | N/A | [architecture/observability/README.md](architecture/observability/README.md), [architecture/cps/CPS_CONTROL_LOOP.md](architecture/cps/CPS_CONTROL_LOOP.md) | Design-level |
| Infrastructure | Sovereign infrastructure is intended to survive cloud loss | SPEC | CONCEPT | Local-first architecture | Not implemented | Not implemented | N/A | [docs/infrastructure/README.md](docs/infrastructure/README.md) | Conceptual |
| Engineering Research | Hypothesis/evidence distinction is enforced as repository policy | POLICY | DESIGN | Epistemic discipline | Enforced by document convention only; no automated check implemented | Not implemented | N/A | [architecture/evidence/EVIDENCE_MODEL.md](architecture/evidence/EVIDENCE_MODEL.md) | Design-level |
| Technical Documentation | Canonical architecture and terminology enable consistent navigation without duplication | SPEC | DESIGN | SSOT and no-duplication | Repository structure exists | Manual link/consistency check performed during this remediation | N/A | [docs/foundations/TERMINOLOGY.md](docs/foundations/TERMINOLOGY.md), [README.md](README.md) | Design-level |

## Explicit Non-Claims

No row above may be interpreted as Implementation-backed, Experiment-backed, Measured, or Verified. No code, hardware, or measured runtime evidence currently exists in this repository. Upgrading any row requires adding a linked artifact under `evidence/`, `measurements/`, `experiments/`, or `tests/` conforming to [schemas/evidence.schema.json](schemas/evidence.schema.json).

## Private Implementation Evidence (Does Not Change Confidence Ratings Above)

Per [architecture/evidence/EVIDENCE_MODEL.md](architecture/evidence/EVIDENCE_MODEL.md)'s Verification Level axis, private-environment artifacts have been directly inspected (FILE-VERIFIED/TEST-VERIFIED) for the Embedded, Edge Computing, and Networking rows above (CoreAgent agent runtime, an Arduino/Flask bridge, a greenhouse controller, embedded firmware, an FSM test suite, and mesh tooling installation). This is real evidence of the author's engineering practice, labeled IMPLEMENTED — PRIVATE in [projects/ericaos/README.md](projects/ericaos/README.md) and the relevant case studies ([CASE-001](case-studies/CASE-001/README.md), [CASE-003](case-studies/CASE-003/README.md), [CASE-004](case-studies/CASE-004/README.md), [CASE-005](case-studies/CASE-005/README.md)). It intentionally does not raise the Confidence column above, because that column scores only what is Implementation-backed *in this public repository*, and none of this evidence has been exported, sanitized, or made publicly reproducible here.
