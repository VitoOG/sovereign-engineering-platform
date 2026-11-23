# Industrial Runtime

Artifact Type: EXPERIMENTAL ENGINEERING RUNTIME / SIMULATION PROJECT

Project Status: MIXED MATURITY

Maturity Status: MIXED (one historical FSM test slice; broader runtime remains an initial scaffold)

Public Repository Status: SANITIZED SOURCE-INVENTORY SUMMARY

## System Role

Industrial Runtime explores deterministic runtime mechanisms for industrial/event-driven systems: finite-state machines, event sourcing, access-control lists, event and command contracts, simulation, metrics, health checks, logging, and tracing.

It is a separate experimental engineering project. It is not the current ERICA OS Go runtime and must not be merged into ERICA's task/workflow authority merely because concepts overlap.

## Historical Source Inventory

The 2026-11-13 static audit reported:

- 31 Python modules.
- 44 classes and 83 functions.
- 11 test modules.
- 4,347 lines in the static code map.

The audit listed source families for:

- Runtime ACL and event/command contracts.
- Finite-state machine (FSM) transitions and guards.
- Event store, event sourcing, replay, snapshots, and correlation.
- Simulator devices and MQTT publisher.
- Observability: health, metrics, logging, and tracing.
- Database migration scaffolding.

The source listing also contained suffixed duplicate-looking files such as `(2).py`. Their provenance and relationship to canonical files were not resolved in that audit. Do not silently select one copy or infer that duplicates are safe to remove.

## Maturity by Component

| Component | Historical state | Evidence boundary |
|---|---|---|
| Typed FSM | IMPLEMENTED — PRIVATE (historical test evidence) | Existing [CASE-003](../../case-studies/CASE-003/README.md) records an earlier persisted `8 passed` result for `tests/test_fsm.py`; this is a bounded FSM result, not a full runtime acceptance |
| ACL | INVENTORIED | Test source files and implementation symbols were mapped; no current execution result |
| Event store / event sourcing | INVENTORIED | Source and test modules mapped; no end-to-end event durability/replay acceptance |
| Simulator / MQTT | INVENTORIED | Modules listed; device and broker behaviour not verified |
| Observability modules | INVENTORIED | Health, metrics, logging, and tracing source families listed; no operational telemetry validation |
| Full Industrial Runtime | INITIAL SCAFFOLD / UNVERIFIED | The historical project description called the surrounding system an initial scaffold; no integrated production runtime is claimed |

## Architectural Boundary

The 2026-11-13 ERICA source disposition classified Industrial Runtime as **ISOLATE**, pending domain and safety-contract assessment.

That disposition means preserve it as a separate source and evaluate it through explicit contracts. It does not mean delete it, merge it into ERICA OS, or declare it unusable.

Conceptual overlap with ERICA's Go workflow is not shared implementation, shared state ownership, or a migration decision.

## Next Verification Gates

1. Locate the canonical source root and pin a revision.
2. Resolve duplicate-suffixed files and nested copies with provenance.
3. Inspect ACL, event, command, and FSM contracts.
4. Re-run the FSM tests; independently run ACL, store, replay, simulator, and observability tests.
5. Verify storage durability, snapshot/replay consistency, event ordering, and failure behaviour.
6. Define whether this project remains a standalone simulator/runtime research project or contributes selected patterns through explicit contracts.
7. Keep ERICA OS task identity, authorization, persistence, and audit authoritative in the ERICA domain unless a separately approved migration is specified.

## Related Case Study

[CASE-010 — Industrial Runtime / Event-Driven Control](../../case-studies/CASE-010/README.md)
