# CASE-007: Observatory + Watchdog Architecture

Artifact Type: CASE STUDY
Maturity: CONCEPT

1. Problem: Need unified observability that supports reliable intervention, not only reporting.
2. Context: Telemetry fragmentation hides system-level failure patterns.
3. Requirements: Multi-layer telemetry ingestion and explicit state synthesis, per the taxonomy in [architecture/cps/CPS_CONTROL_LOOP.md](../../architecture/cps/CPS_CONTROL_LOOP.md).
4. Constraints: Event volume, schema drift, time synchronization.
5. Threat Model: Blind spots, alert fatigue, telemetry tampering. See [architecture/security/THREAT_MODEL.md](../../architecture/security/THREAT_MODEL.md).
6. Architecture: Observatory -> System State -> Watchdog -> Failure Detection -> Recovery. See [architecture/observability/README.md](../../architecture/observability/README.md).
7. Design: [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md) defines the detection/recovery stages this case relies on (DESIGN maturity).
8. Implementation: NOT IMPLEMENTED.
9. Tests: NOT IMPLEMENTED — state reconstruction consistency and watchdog policy tests are planned.
10. Measurements: NOT IMPLEMENTED.
11. Failures: NOT IMPLEMENTED — potential false positives/negatives in the detection path are an anticipated design risk, not an observed failure.
12. Recovery: Escalation policy and recovery workflow per [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md); not implemented.
13. Evidence: None.
14. Limitations: Runtime KPI evidence does not exist.
15. Lessons: Observability must be operationally actionable, not only a reporting surface.
16. Next Iteration: Define a canonical event taxonomy and confidence scoring scheme as a DESIGN-level addendum.
17. Maturity: CONCEPT
