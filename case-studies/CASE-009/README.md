# CASE-009: CAR-TWIN Digital Twin Capture

Artifact Type: CASE STUDY

Maturity: MIXED — historical source inventory identifies a substantial Python application and test suite; current execution, calibration, and physical accuracy are NOT VERIFIED

1. Problem: Capture repeatable views of a physical object or scene using coordinated camera and rotary motion, while preserving capture state and dataset provenance.
2. Context: A capture workflow spans camera interfaces, motion hardware, serial communication, calibration, orchestration, and reconstruction. Failure at any boundary can produce incomplete or mislabeled datasets.
3. Requirements: Explicit capture state; bounded rotary motion; camera abstraction; serial protocol handling; calibration; deterministic capture orchestration; dataset manifests and checkpointing; recoverable failure handling.
4. Constraints: Camera/device compatibility, turntable geometry, encoder accuracy, mechanical limits, serial latency, lighting, object geometry, and reconstruction assumptions. Numerical limits remain [UNRESOLVED_SPEC: Requires Hardware/Code Verification].
5. Threat Model: Unexpected motion, stale or malformed serial data, camera disconnect, partial capture, duplicate/overwritten frames, invalid calibration, and inconsistent dataset metadata.
6. Architecture: The historical source map identified a Python application with a CaptureOrchestrator, SerialTurntableController, camera abstraction, motion planner, digital-twin model, simulated adapters, and reconstruction interfaces. See [projects/car-twin](../../projects/car-twin/README.md).
7. Design: The static code map recorded 32 Python modules, 24 classes, 37 functions, and distinct capture, hardware, motion, and state-machine areas. This is a historical inventory, not a current architecture review.
8. Implementation: Historical source inventory identified 32 Python modules and 1,311 lines. Source tree and exact revision were not re-inspected during this public SEP update.
9. Tests: Four test modules were inventoried: `test_capture.py`, `test_hardware.py`, `test_motion.py`, and `test_state_machine.py`. Test presence is not proof of passing tests; no current execution result is claimed.
10. Measurements: No camera calibration error, turntable positional accuracy, capture repeatability, reconstruction quality, or throughput measurement is claimed.
11. Failures: Failure scenarios identified by test names include simulated capture, hardware protocol handling, and failed-frame recapture. Actual incident history was not located.
12. Recovery: Checkpoint and recapture mechanisms were identified in the source inventory; their runtime correctness and non-overwrite guarantees require re-testing.
13. Evidence: Historical source inventory and static code map in `ERICAOS-FUNCTIONAL-STATE-20261113T015820Z.txt`, dated 2026-11-13. No public source export or linked Evidence record exists in this repository.
14. Limitations: No current source revision, repeatable build, test log, HIL result, calibration report, or independently reproduced dataset exists here.
15. Lessons: Capture completeness, mechanical repeatability, and digital-twin fidelity are separate claims and require separate evidence.
16. Next Iteration: Pin the canonical source revision; recreate environment; run all four test modules; validate serial protocol; calibrate camera/turntable geometry; perform bounded HIL tests; record repeatability and reconstruction metrics.
17. Maturity: MIXED — historical IMPLEMENTATION inventory; no current runtime or measurement verification.
