# Golden Greens Crop — CEA / AgTech R&D

Artifact Type: APPLIED R&D DOMAIN

Project Status: MIXED MATURITY

Maturity Status: MIXED (engineering/control artifacts and biological outcomes are assessed separately)

Public Repository Status: SANITIZED ARCHITECTURE / EVIDENCE SUMMARY

## System Role

Golden Greens Crop is the applied R&D and business domain in which systems integration is applied to controlled-environment agriculture, instrumentation, environmental monitoring, and cyber-physical automation.

It is not the owner of the generic ERICA OS runtime, SEP architecture governance, or shared infrastructure. It is an applied domain that consumes shared engineering capabilities.

## Scope

- Controlled-environment agriculture (CEA) and AgTech.
- Hydroponic, aeroponic, and aquaponic system engineering.
- Environmental and nutrient-solution measurement.
- Sensor, embedded-controller, edge-service, and backend integration.
- Crop steering and cultivation-process automation research.
- Measurement, experimental design, and separation of engineering performance from biological outcomes.

## Project Structure

| Sub-project / capability | Relationship | Public profile |
|---|---|---|
| Smart Greenhouse Controller | Applied controller/backend child project | [projects/smart-greenhouse](../smart-greenhouse/README.md) |
| Deterministic Controller | Shared embedded/control capability; not a second greenhouse project | [projects/deterministic-controller](../deterministic-controller/README.md) |
| ERICA OS | Reusable engineering runtime and evidence/workflow environment | [projects/ericaos](../ericaos/README.md) |

The ATmega4809 firmware described by CASE-003 and CASE-005 is a shared artifact reference. Do not count it as two independent firmware implementations.

## Historical Source Inventory

The 2026-11-13 source inventory reported:

- `PROJECTS_01-PRODUCTS_GOLDEN-GREENS`: 70 discovered files.
- 5 test-related files and 8 build/manifest files.
- No Git metadata location detected in that inventory pass.

These are inventory counts, not evidence that the tests passed, the complete source tree was captured, or a greenhouse was commissioned.

## Evidence and Maturity

| Claim area | Current classification | Boundary |
|---|---|---|
| CEA engineering direction | DESIGN / R&D | Domain scope and intended engineering direction |
| Smart Greenhouse controller and firmware | IMPLEMENTED — PRIVATE, FILE-VERIFIED in the historical audit | See [CASE-005](../../case-studies/CASE-005/README.md); this does not establish current operation |
| Deterministic FSM test slice | Historical TEST-VERIFIED claim for the FSM slice only | See [CASE-003](../../case-studies/CASE-003/README.md); not a greenhouse HIL result |
| Agronomic / biological outcomes | HYPOTHESIS / UNMEASURED | No verified yield, growth, or crop-quality data is claimed |
| Integrated commissioned greenhouse | NOT VERIFIED | No end-to-end commissioning or field acceptance record was located |

## Safety and Authority

AI may analyse sensor history, identify anomalies, draft test plans, and recommend parameter changes. It does not directly command pumps, dosing, heating, lighting, thyristors, valves, or other physical loads.

Any physical action remains within a deterministic controller, explicit operating envelope, and independent safety boundary. See [CASE-003](../../case-studies/CASE-003/README.md), [CASE-005](../../case-studies/CASE-005/README.md), and [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md).

## Next Verification Gates

1. Reconcile current Golden Greens and Smart Greenhouse source roots with the 2026-11-13 inventory.
2. Identify the canonical firmware/backend versions and their commit or content hashes.
3. Re-run controller-specific tests in an isolated environment.
4. Define electrical, protocol, calibration, interlock, and safe-state contracts.
5. Perform bench and hardware-in-the-loop verification before claiming physical integration.
6. Design separate agronomic experiments with measured outcomes and linked Evidence records.

## Related Case Studies

- [CASE-003 — Deterministic Cyber-Physical Controller](../../case-studies/CASE-003/README.md)
- [CASE-005 — Smart Greenhouse / Controlled Environment](../../case-studies/CASE-005/README.md)
