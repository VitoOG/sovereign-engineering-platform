# Deterministic Control (Summary)

Artifact Type: SPEC
Maturity Status: DESIGN

Canonical contracts (authoritative, do not re-derive):

- Layer authority for deterministic control: [architecture/LAYER_CONTRACTS.md](../../architecture/LAYER_CONTRACTS.md#l1-embedded)
- AI authority separation: [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md)
- Failure/recovery contract: [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md)

Techniques in scope: finite-state machines, watchdogs, hysteresis, debouncing, sensor validation, interlocks, safe states, degraded operation, recovery verification.

Safety note: do not set numeric safety thresholds without verified hardware/software evidence; use `[UNRESOLVED_SPEC: Requires Hardware/Code Verification]`.
