# Smart Greenhouse Controller

Artifact Type: APPLIED CPS PROJECT

Project Status: MIXED MATURITY

Maturity Status: MIXED (private controller artifacts; no verified integrated field outcome)

Parent Domain: [Golden Greens Crop](../golden-greens/README.md)

Public Repository Status: SANITIZED ARCHITECTURE / EVIDENCE SUMMARY

## System Role

The Smart Greenhouse Controller is the controller/backend project within the Golden Greens applied CEA domain. It connects sensor acquisition, serial communication, environmental process state, and bounded automation functions.

It is a child project of Golden Greens Crop, not a separate company or a competing general-purpose platform.

## Historical Source Inventory

The 2026-11-13 inventory reported:

- 98 discovered files under the Smart Greenhouse source root.
- 2 test-related files and 13 build/manifest files.
- 2 Git metadata locations.

The deeper audit identified the `GREENHOUSE-CONTROLLER` source family, including Python API/routes, application entry points, driver modules, crop-steering logic, and Arduino firmware. Inventory presence is not a test result.

## Observed / Reported Components

| Component | Evidence state | Qualification |
|---|---|---|
| Flask + Socket.IO controller service | IMPLEMENTED — PRIVATE, FILE-VERIFIED in the historical project audit | Source described a 24-field serial CSV protocol and background service logic |
| REST API | IMPLEMENTED — PRIVATE, FILE-VERIFIED in the historical project audit | Routes covered automation, pump, thyristor, light recipes, and growth-cycle stages |
| Serial integration | IMPLEMENTED — PRIVATE, FILE-VERIFIED in the historical project audit | Reconnect/retry logic and serial parsing were inspected in the earlier audit |
| `IntegratedController.ino` firmware | Shared with the deterministic-controller evidence line | Do not duplicate it as a separate firmware asset; see [projects/deterministic-controller](../deterministic-controller/README.md) |
| Controller-specific automated tests | NOT VERIFIED | No persisted test result for this controller was located in the historical report |
| Hardware-in-the-loop / commissioning | NOT VERIFIED | No HIL or field commissioning evidence was located |
| Crop/yield/agronomic outcomes | UNMEASURED | No measured biological outcome is claimed |

## Architecture Boundaries

- The controller/backend is distinct from the generic ERICA OS runtime.
- The deterministic controller is the authority for physical actuation.
- Network/API availability does not replace local controller interlocks or safe states.
- Telemetry is an observation channel, not proof that measurements are accurate or calibrated.
- AI remains advisory and cannot directly actuate physical loads.

## Integration Relationships

| Related item | Relationship |
|---|---|
| [Golden Greens Crop](../golden-greens/README.md) | Parent applied R&D domain |
| [Deterministic Controller](../deterministic-controller/README.md) | Shared embedded/control capability and firmware lineage |
| [ERICA OS](../ericaos/README.md) | Reusable engineering workflow, knowledge, and runtime environment; not the owner of greenhouse control |
| [CASE-005](../../case-studies/CASE-005/README.md) | Existing Smart Greenhouse / CEA case study |
| [CASE-003](../../case-studies/CASE-003/README.md) | Related deterministic controller and FSM evidence |

## Next Verification Gates

1. Identify the canonical controller source tree and firmware revision.
2. Resolve duplicate/legacy entry points and configuration variants.
3. Reproduce backend and firmware build/test procedures.
4. Specify and validate serial framing, field ordering, units, timeout, reconnect, and stale-data behaviour.
5. Verify actuator startup/shutdown, interlocks, watchdogs, and failure states on a safe bench.
6. Separate control-system acceptance from agronomic experiment acceptance.

No production deployment, commercial greenhouse scale, yield improvement, or physical safety certification is claimed.
