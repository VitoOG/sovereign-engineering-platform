# Observatory and Watchdog

Artifact Type: SPEC
Maturity Status: DESIGN

Telemetry taxonomy this model consumes: [architecture/cps/CPS_CONTROL_LOOP.md](../cps/CPS_CONTROL_LOOP.md)

Aggregation levels:

- Device
- Room/Zone
- Building
- Facility
- District
- City

Flow:

Telemetry -> Observatory -> Explicit System State -> Watchdog -> Failure Detection -> Recovery

Observability is a state-construction and control-support mechanism.

## Observability Architecture (Design)

```mermaid
flowchart TD
    T1[Sensor Telemetry] --> OBS[Observatory]
    T2[Control Telemetry] --> OBS
    T3[Actuator Feedback] --> OBS
    T4[Security Telemetry] --> OBS
    T5[AI/Agent Telemetry] --> OBS

    OBS --> SS[Explicit System State]
    SS --> WD[Watchdog]
    WD -->|anomaly| FD[Failure Detection]
    WD -->|nominal| SS
    FD --> RC[Recovery Workflow]
    RC -->|per FAILURE_AND_RECOVERY_MODEL| SS
```

Source taxonomy: [architecture/cps/CPS_CONTROL_LOOP.md](../cps/CPS_CONTROL_LOOP.md). Recovery workflow: [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../reliability/FAILURE_AND_RECOVERY_MODEL.md). No runtime implementation exists in this repository.
