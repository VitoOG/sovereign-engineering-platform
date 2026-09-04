# CPS Architecture

Artifact Type: SPEC
Maturity Status: DESIGN

Canonical model (authoritative): [architecture/cps/CPS_CONTROL_LOOP.md](CPS_CONTROL_LOOP.md)

Summary only, not a redefinition:

Physical World -> Sensors -> Acquisition -> Validation -> State Estimation -> Deterministic Control -> Actuation -> Physical World

Telemetry is emitted by every stage (see CPS_CONTROL_LOOP.md telemetry taxonomy), not by a single point. Knowledge/AI consumes aggregated telemetry via the Observatory and can only reach Actuation through [architecture/security/AI_AUTHORITY_CONTRACT.md](../security/AI_AUTHORITY_CONTRACT.md).

Safety rule:

No uncontrolled LLM to GPIO/relay/dosing/pump path.
