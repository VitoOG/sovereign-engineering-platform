# Deterministic Cyber-Physical Controller

Artifact Type: PROJECT

Maturity Status: MIXED MATURITY

Implementation Status:
IMPLEMENTED COMPONENTS — PRIVATE (firmware, FSM test suite)

Public Repository Status:
SANITIZED EVIDENCE / ARCHITECTURE

## System Scope

A policy-gated deterministic controller where physical actuation authority is isolated from AI recommendation. See [architecture/cps/CPS_CONTROL_LOOP.md](../../architecture/cps/CPS_CONTROL_LOOP.md) and [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md).

## Implemented Components

| Component | Status | Evidence |
|---|---|---|
| Embedded firmware (`IntegratedController.ino`, ATmega4809) | IMPLEMENTED — PRIVATE | FILE-VERIFIED: sensor acquisition (DHT11 x2, DS18B20 x2, pH, TDS, gas, float switch), non-blocking `millis()` scheduling, pH calibration table + Nernst compensation, PWM pump + thyristor actuation |
| Typed FSM runtime (`src/runtime/fsm.py`) | IMPLEMENTED — PRIVATE | EXECUTED / TESTED: persisted pytest log recorded `8 passed` for `tests/test_fsm.py` (transition guards, history, metrics) |

## Architecture Components

| Component | Status | Evidence |
|---|---|---|
| Controller architecture | ARCHITECTURE | [architecture/LAYER_CONTRACTS.md](../../architecture/LAYER_CONTRACTS.md#l1-embedded) design documentation |
| Fault detection / interlocks | ARCHITECTURE | [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md); no code inspected implementing interlocks specifically |
| Degraded mode / recovery logic | ARCHITECTURE | Same document; not implemented/tested end-to-end |
| AI recommendation boundary | ARCHITECTURE | [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md); no enforcement code found in either environment |
| Physical actuation (hardware-in-the-loop) | HARDWARE-DEPENDENT, NOT VERIFIED | Firmware exists (above); no evidence of on-hardware test was found |
| Production CPS deployment | NOT VERIFIED | No deployment evidence found anywhere |

## Evidence

Source files and one persisted test log were opened and read directly by the assistant in a private engineering environment (not this repository). Full detail: [case-studies/CASE-003/README.md](../../case-studies/CASE-003/README.md).

## Verification Boundaries

FILE-VERIFIED and EXECUTED/TESTED apply only to the specific firmware excerpt and FSM test suite inspected. No hardware-in-the-loop test, no fault-injection test, and no integrated firmware+FSM system test have been observed.

## Known Gaps

Safety thresholds, watchdog timeouts, and actuator saturation limits are `[UNRESOLVED_SPEC: Requires Hardware/Code Verification]` — not fabricated.

## Reproducibility

Public Reproducibility: none (PUBLIC-VERIFIED not met). No source, firmware, or test file has been exported into this repository.

## Public / Private Boundary

Private: full firmware and FSM source, private test logs. Public: this architecture summary and the linked case study only.
