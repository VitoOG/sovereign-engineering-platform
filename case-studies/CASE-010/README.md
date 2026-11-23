# CASE-010: Industrial Runtime / Event-Driven Control

Artifact Type: CASE STUDY

Maturity: MIXED — FSM test slice historically TEST-VERIFIED; broader runtime remains an initial scaffold / UNVERIFIED

1. Problem: Explore deterministic state transitions and event-driven coordination for industrial workflows under partial failure and changing device state.
2. Context: Industrial applications require explicit state ownership, guarded transitions, auditable events, access control, simulation, and observability. A module inventory alone does not establish a production runtime.
3. Requirements: Typed FSM; guarded transitions; event/command contracts; event persistence and replay; access-control boundaries; simulator adapters; health/metrics/logging/tracing; migration discipline; deterministic failure behaviour.
4. Constraints: Event ordering, persistence durability, schema evolution, clock consistency, device protocol variability, broker availability, and authorization scope. Exact guarantees remain [UNRESOLVED_SPEC: Requires Hardware/Code Verification].
5. Threat Model: Unauthorized state transitions, replay or duplicate events, stale device state, corrupted event history, privilege escalation, MQTT broker compromise, and misleading telemetry.
6. Architecture: Historical inventory identified a Python runtime organized around ACL, contracts, FSM, event store/event sourcing, simulator/device adapters, MQTT publishing, migrations, and observability. See [projects/industrial-runtime](../../projects/industrial-runtime/README.md).
7. Design: The historical static map recorded 31 Python modules, 44 classes, 83 functions, 11 test modules, and 4,347 lines. The surrounding project description characterized the wider runtime as an initial scaffold.
8. Implementation: A typed FSM slice was identified as implemented privately. The broader ACL, event-sourcing, simulator, and observability layers remain inventory findings, not an integrated implementation claim.
9. Tests: A historical persisted pytest log recorded `8 passed` for `tests/test_fsm.py` only, as documented in CASE-003. Eleven test modules were inventoried for the wider runtime; no current full-suite run is claimed.
10. Measurements: No event throughput, latency, durability, replay consistency, recovery time, or resource measurements are claimed.
11. Failures: Failure modes are architectural test targets; no complete runtime incident dataset was located.
12. Recovery: Replay, snapshots, and event-store recovery are candidate mechanisms; durability and crash-consistency must be tested before being described as operational recovery.
13. Evidence: Historical static code map and project audit index in `ERICAOS-FUNCTIONAL-STATE-20261113T015820Z.txt`, dated 2026-11-13; earlier FSM test result is referenced in CASE-003. No public source or linked Evidence record exists here.
14. Limitations: Duplicate-suffixed source files were observed in the historical inventory; provenance and canonical-file selection remain unresolved. No end-to-end runtime acceptance is claimed.
15. Lessons: A passing FSM unit suite does not validate event persistence, ACL enforcement, broker integration, simulator fidelity, or industrial deployment.
16. Next Iteration: Pin canonical source revision; resolve duplicate files; execute each test module; test event ordering/durability/replay; validate ACL denial paths; exercise broker and device failures; define a bounded integration acceptance suite.
17. Maturity: MIXED — FSM slice historically TEST-VERIFIED; complete Industrial Runtime NOT VERIFIED.
