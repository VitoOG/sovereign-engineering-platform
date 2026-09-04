# CASE-005: Smart Greenhouse / Controlled Environment

Artifact Type: CASE STUDY
Maturity: MIXED — engineering/control system is IMPLEMENTED — PRIVATE; biological/agronomic outcome claims remain HYPOTHESIS

1. Problem: Operate biological environment with reliable climate, water, and light control.
2. Context: Biological variability and physical constraints demand robust control loops.
3. Requirements: Sensor fusion, deterministic control, telemetry, anomaly detection.
4. Constraints: Biological response delay, noisy inputs, seasonal variation.
5. Threat Model: Sensor drift, actuator lock, unsafe dosing path. See [architecture/security/THREAT_MODEL.md](../../architecture/security/THREAT_MODEL.md). Unsafe dosing is explicitly prohibited from an uncontrolled AI path per [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md).
6. Architecture: CPS loop with policy-gated actuation and observability. See [architecture/cps/CPS_CONTROL_LOOP.md](../../architecture/cps/CPS_CONTROL_LOOP.md).
7. Design: NOT IMPLEMENTED in this repository — no dosing/climate control design document exists here beyond this case study.
8. Implementation: IMPLEMENTED — PRIVATE, FILE-VERIFIED, in a separate private codebase (not in this repository): a Flask + Socket.IO controller service (`app.py`) documenting a 24-field serial CSV protocol from Arduino, a REST API (`/api/v1/*`: automation, pump, thyristor, light recipes, growth-cycle stages), serial reconnect/retry logic, and thread-safety notes for its background threads; paired with the same `IntegratedController.ino` embedded firmware described in [CASE-003](../CASE-003/README.md) (shared artifact, not duplicated here). This project's own documentation explicitly labels it "production-ready" as an internal claim — that label is not adopted here without independent runtime/measurement evidence.
9. Tests: NOT IMPLEMENTED for this controller specifically — no persisted test log was found for it (contrast with the separate FSM test evidence in CASE-003).
10. Measurements: NOT IMPLEMENTED — no climate/yield/agronomic measurement data was found or inspected.
11. Failures: NOT IMPLEMENTED — no failure-mode log was found.
12. Recovery: Safe-state fallback and staged restart intended per [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md); not implemented as a tested procedure.
13. Evidence: Source code was opened and read directly by the assistant (FILE-VERIFIED). No lab or field measurement, and no biological/agronomic outcome evidence, was found or inspected. No linked Evidence record exists in this repository.
14. Limitations: No verified agronomic, yield, or biological outcome claims are made or implied by this case study, regardless of claims made in the private project's own documentation.
15. Lessons: A real, working control-and-telemetry engineering system can coexist with zero verified biological/agronomic outcome evidence — these are independent claims and must be scored independently.
16. Next Iteration: Define an experiment protocol with provenance conforming to [schemas/evidence.schema.json](../../schemas/evidence.schema.json), separating control-system verification from agronomic outcome verification.
17. Maturity: MIXED (see line 2 above)
