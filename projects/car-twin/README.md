# CAR-TWIN — Digital Twin Capture

Artifact Type: ENGINEERING APPLICATION / PROTOTYPE CANDIDATE

Project Status: MIXED MATURITY

Maturity Status: IMPLEMENTATION (historical source-inventory basis; verification remains unresolved)

Public Repository Status: INVENTORY SUMMARY ONLY — source and datasets are not published here

## System Role

CAR-TWIN is a capture and reconstruction application combining camera operation, a controlled rotary/turntable interface, motion planning, capture orchestration, calibration, dataset manifests, and a digital-twin representation.

It is a distinct engineering application. It is not a subsystem of ERICA OS and is not part of the Smart Greenhouse controller.

## Historical Inventory Evidence

The 2026-11-13 source audit recorded:

- 32 Python modules.
- 24 classes and 37 functions.
- 4 test modules.
- 1,311 lines in the static code map.

The inventory identified modules for camera capture, serial turntable control, simulated adapters, hardware interfaces, encoder conversion, motion planning, state management, digital-twin models, dataset manifests, and reconstruction interfaces.

This is a historical source inventory. The underlying source tree was not re-inspected or executed as part of this public-repository reconciliation.

## Identified Functional Areas

| Area | Inventory evidence | Verification boundary |
|---|---|---|
| Capture orchestration | `CaptureOrchestrator`, checkpoint/accept flow | Source symbols inventoried; runtime not re-tested |
| Rotary/turntable control | `SerialTurntableController`, serial protocol encoder/parser | Protocol and hardware behaviour not re-verified |
| Camera abstraction | Camera controller interfaces and adapters | Device compatibility not re-verified |
| Motion planning | Position planner and angular-error helpers | Determinism assertions exist in test source; not re-run here |
| Digital twin | Digital-twin model package | Model validity and physical correspondence not measured |
| Dataset integrity | Manifest/checkpoint/hash-related capture flow | No independent dataset audit performed |
| Simulation | Simulated adapters | Simulation boundary and fidelity not validated |

## Tests and Measurements

Four test modules were present in the historical inventory:

- `tests/test_capture.py`
- `tests/test_hardware.py`
- `tests/test_motion.py`
- `tests/test_state_machine.py`

The test names include deterministic motion, serial protocol handling, simulated capture, and failed-frame recapture without overwrite. Their presence does **not** establish that they passed. No current test execution, benchmark, camera calibration result, positional accuracy measurement, or reconstruction-quality metric is claimed.

## Safety and Operational Boundaries

Any physical rotary or camera-positioning mechanism requires explicit travel limits, timeout behaviour, emergency-stop semantics, collision constraints, and verified feedback. A digital-twin model is not proof of physical accuracy. No AI-to-actuator authority is implied by this project profile.

## Relationship to the Ecosystem

- Shared engineering principles and evidence rules are governed by this SEP repository.
- ERICA OS may eventually provide evidence, workflow, and project-context services, but no runtime integration is established.
- CAR-TWIN remains a separate application candidate; it is not merged into ERICA OS or Golden Greens by this profile.

## Next Verification Gates

1. Locate and pin the canonical source repository/revision.
2. Reconcile inventory paths and any duplicate/nested copies.
3. Recreate a clean environment from the manifest.
4. Run the four test modules and preserve raw logs.
5. Verify serial protocol and simulated/physical adapter equivalence.
6. Calibrate camera and turntable geometry.
7. Define repeatability, capture completeness, and reconstruction acceptance metrics.
8. Link measured results to Evidence records before making accuracy or performance claims.

## Related Case Study

[CASE-009 — CAR-TWIN Digital Twin Capture](../../case-studies/CASE-009/README.md)
