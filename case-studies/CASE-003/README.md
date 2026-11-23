# CASE-003: Deterministic Cyber-Physical Controller

Artifact Type: CASE STUDY
Maturity: MIXED MATURITY — firmware and FSM test suite are IMPLEMENTED — PRIVATE; integrated system and hardware deployment are ARCHITECTURE only

1. Problem: Ensure safe physical control under uncertainty and partial failure.
2. Context: CPS systems fail at boundaries between sensing, logic, and actuation.
3. Requirements: FSM control, sensor validation, interlocks, safe states, watchdog.
4. Constraints: Sensor noise, actuator delays, hardware faults.
5. Threat Model: Faulty sensor input, unauthorized command path, network outage. See [architecture/security/THREAT_MODEL.md](../../architecture/security/THREAT_MODEL.md).
6. Architecture: Policy-gated deterministic control core. See [architecture/LAYER_CONTRACTS.md](../../architecture/LAYER_CONTRACTS.md#l1-embedded) and [architecture/cps/CPS_CONTROL_LOOP.md](../../architecture/cps/CPS_CONTROL_LOOP.md).
7. Design: [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md) defines the recovery contract (DESIGN maturity, this repository).
8. Implementation: IMPLEMENTED — PRIVATE, FILE-VERIFIED, in two separate private codebases (not in this repository): (a) embedded firmware (`IntegratedController.ino`) with non-blocking `millis()` scheduling, DHT11 x2, DS18B20 x2, pH on A1 with a calibration table and Nernst temperature compensation, TDS/EC on A6, gas sensor on A2, float switch on A0, PWM pump control, and a thyristor output; (b) a typed FSM runtime (`src/runtime/fsm.py`) with transition guards, history, and metrics, part of a larger "Industrial Event Runtime Simulator" project whose own README states it is at "Initial Scaffold" for the surrounding event-sourcing/observability layers.
9. Tests: TEST-VERIFIED for the FSM slice only — a persisted pytest log recorded `8 passed` for `tests/test_fsm.py`. Fault injection and degraded-mode transition tests for the embedded firmware are NOT IMPLEMENTED.
10. Measurements: NOT IMPLEMENTED — no quantified control-loop performance data exists.
11. Failures: NOT IMPLEMENTED — no runtime exists to observe end-to-end failures across firmware and FSM together.
12. Recovery: Detect -> Isolate -> Degrade -> Recover -> Verify per [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md); not implemented as an integrated, tested workflow.
13. Evidence: Source files and a persisted test log were opened and read directly by the assistant (FILE-VERIFIED, TEST-VERIFIED for the FSM tests). No Evidence record exists in this repository's evidence/, measurements/, or tests/.
14. Limitations: Threshold values (pH/EC target bands, watchdog timeouts, actuator saturation limits) intentionally unspecified: [UNRESOLVED_SPEC: Requires Hardware/Code Verification].
15. Lessons: Determinism must be designed before it can be claimed as a safety feature; a passing unit-test suite for an FSM is not the same as a verified physical control loop.
16. Next Iteration: Create a formal state-transition test matrix aligned to [schemas/recovery-event.schema.json](../../schemas/recovery-event.schema.json), and connect the FSM runtime to the actual firmware in an integration test.
17. Maturity: MIXED MATURITY (public repository remains ARCHITECTURE; private firmware/FSM are IMPLEMENTED — PRIVATE per [projects/deterministic-controller/README.md](../../projects/deterministic-controller/README.md))
