# ERICAOS

Artifact Type: FLAGSHIP ARCHITECTURE

Maturity Status: MIXED MATURITY (see component table)

Implementation Status:
IMPLEMENTED COMPONENTS — PRIVATE (agent runtime, local inference, Arduino bridge, service supervision, tests)

Public Repository Status:
SANITIZED EVIDENCE / ARCHITECTURE

ERICAOS is an actively engineered local-first cyber-physical runtime and architecture. Maturity is classified per component, not as a single project-wide label, per [architecture/evidence/EVIDENCE_MODEL.md](../../architecture/evidence/EVIDENCE_MODEL.md). A single project may legitimately contain CONCEPT, ARCHITECTURE, and IMPLEMENTED — PRIVATE components at once. Absence from this public repository does not mean CONCEPT; it means the artifact has not been exported here.

## System Scope

Layers: L0 Physical, L1 Embedded, L2 Edge, L3 Network, L4 Data/Knowledge, L5 Intelligence, L6 Evolution. Core loop: Observe -> State -> Understand -> Decide -> Act -> Verify -> Measure -> Learn -> Improve.

## Implemented Components

| Component | Status | Evidence Level | Evidence Basis |
|---|---|---|---|
| Agent runtime (CoreAgent) | IMPLEMENTED — PRIVATE | FILE-VERIFIED | Source inspected directly: `core/agent.py`, `models/model_manager.py`, `models/router.py`, provider fallback chain logic |
| Local inference (llama-server + Qwen2.5-0.5B GGUF) | IMPLEMENTED — PRIVATE | FILE-VERIFIED | Model file and systemd unit (port 8090, ctx 2048, hardened with `ProtectSystem=strict`) inspected directly |
| Edge/Arduino bridge (Flask/SocketIO/pyserial) | IMPLEMENTED — PRIVATE | FILE-VERIFIED | Source inspected directly: reconnect logic, serial parsing |
| Service supervision (systemd units, Raspberry Pi host) | IMPLEMENTED — PRIVATE (enabled state only) | FILE-VERIFIED (unit files); SELF-REPORTED (enabled-state listing) | Unit files inspected directly; a separate host's `systemctl list-unit-files` output lists `ericaos-llm.service`, `flask.service`, `tailscaled.service` as `enabled` — enabled is not the same as currently running, which was not observed |
| Automated tests (CoreAgent) | IMPLEMENTED — PRIVATE | EXECUTED / TESTED | Two pytest files inspected directly; a persisted bootstrap log recorded `5 passed, 8 warnings` and `.pytest_cache/` confirms prior execution |

## Architecture Components

| Component | Status | Evidence Basis |
|---|---|---|
| Layer contracts (L0-L6) | ARCHITECTURE | [architecture/LAYER_CONTRACTS.md](../../architecture/LAYER_CONTRACTS.md) |
| AI authority contract | ARCHITECTURE | [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md) |
| CPS control loop / deterministic actuation boundary | ARCHITECTURE | [architecture/cps/CPS_CONTROL_LOOP.md](../../architecture/cps/CPS_CONTROL_LOOP.md); no firmware/actuator code inspected under this project (see [projects/deterministic-controller](../deterministic-controller/README.md) for the related private firmware) |
| Physical integration (sensors/actuators/dosing) | CONCEPT / R&D | `[UNRESOLVED_SPEC: Requires Hardware/Code Verification]`; not inspected under this project |
| Evolution loop | ARCHITECTURE | [architecture/evolution/README.md](../../architecture/evolution/README.md) |

## Evidence

Do not treat "IMPLEMENTED — PRIVATE" above as "PARTIAL IMPLEMENTATION of the public repository." It means an artifact was directly inspected in a private engineering environment and has not been exported, sanitized, or verified for public reproducibility.

## Verification Boundaries

No component has reached RUNTIME-VERIFIED or PUBLIC-VERIFIED status: no live process or listening service was directly observed for any ERICAOS component during this audit, and no artifact has been exported into this repository with reproducible instructions.

## Known Gaps

Physical integration (sensors/actuators/dosing) has no private evidence located under this project. CPS actuation boundary enforcement code was not found in either environment.

## Reproducibility

Public Reproducibility: none (PUBLIC-VERIFIED not met).

## Public / Private Boundary

Private: CoreAgent, Arduino bridge, systemd units, test logs. Public: this project page and the linked canonical architecture documents below.

- [architecture/LAYER_CONTRACTS.md](../../architecture/LAYER_CONTRACTS.md)
- [architecture/cps/CPS_CONTROL_LOOP.md](../../architecture/cps/CPS_CONTROL_LOOP.md)
- [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md)
