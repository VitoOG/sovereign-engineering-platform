# Canonical Architecture

Artifact Type: SPEC (top-level index)
Maturity Status: DESIGN

## Core Position

This repository documents systems engineering capability across physical, digital, and decision layers.

Main thesis:

- Complex real-world systems are cybernetic systems constrained by physics, resources, information, authority, and law.
- AI is a reasoning and orchestration layer, not uncontrolled physical authority.

## Canonical Pipeline

Authoritative, detailed version with telemetry taxonomy and feedback flow: [architecture/cps/CPS_CONTROL_LOOP.md](architecture/cps/CPS_CONTROL_LOOP.md). This diagram is a summary only and must not be treated as an alternate definition.

```mermaid
flowchart TD
    A[PHYSICAL WORLD] --> B[SENSORS]
    B --> C[ACQUISITION]
    C --> D[VALIDATION]
    D --> E[STATE ESTIMATION]
    E --> F[DETERMINISTIC CONTROL]
    F --> G[ACTUATION]
    G --> A
    E -.telemetry.-> H[KNOWLEDGE / OBSERVATORY]
    F -.telemetry.-> H
    H --> I[LOCAL AI]
    I --> J[ENGINEERING DECISION]
    J --> K[POLICY VALIDATION]
    K --> F
    K --> L[EVOLUTION]
```

## Foundation to Evidence Stack

```mermaid
flowchart TD
    F0[FOUNDATION] --> F1[FUNDAMENTAL LAWS]
    F1 --> F2[SYSTEM MODEL]
    F2 --> F3[ARCHITECTURE]
    F3 --> F4[ENGINEERING]
    F4 --> F5[IMPLEMENTATION]
    F5 --> F6[MEASUREMENT]
    F6 --> F7[EVIDENCE]
    F7 --> F8[EVOLUTION]
```

## Authority Separation

Detailed contract: [architecture/security/AI_AUTHORITY_CONTRACT.md](architecture/security/AI_AUTHORITY_CONTRACT.md).

```mermaid
flowchart TD
    AI[AI / Agent] --> R[Recommendation]
    R --> V[Validation]
    V --> P[Policy]
    P --> C[Deterministic Control]
    C --> E[Firmware / PLC / Edge]
    E --> A[Actuators]
```

Critical rule:

- No uncontrolled LLM to GPIO/relay/dosing/pump path.

## CPS Runtime Model

Superseded by [architecture/cps/CPS_CONTROL_LOOP.md](architecture/cps/CPS_CONTROL_LOOP.md); retained here only as a compact summary consistent with that document.

```mermaid
flowchart TD
    PW[Physical World] --> S[Sensors]
    S --> AQ[Acquisition]
    AQ --> VA[Validation]
    VA --> ST[State Estimation]
    ST --> CT[Deterministic Control]
    CT --> AC[Actuators]
    AC --> PW

    ST --> TM[State Telemetry]
    CT --> TM2[Control Telemetry]
    TM --> KN[Knowledge]
    TM2 --> KN
    KN --> RG[RAG]
    RG --> LA[Local AI]
    LA --> ED[Engineering Decision]
    ED --> CV[Policy Validation]
    CV --> CP[Approved Command]
    CP --> CT
```

## Layer Contracts

Full per-layer contracts (responsibility, inputs, outputs, state ownership, authority, failure behavior, recovery responsibility, evidence): [architecture/LAYER_CONTRACTS.md](architecture/LAYER_CONTRACTS.md).

- L0 Physical
- L1 Embedded
- L2 Edge
- L3 Network
- L4 Data/Knowledge
- L5 Intelligence
- L6 Evolution

## Reliability Contract

Full model with failure classes, detection sources, and per-stage contracts: [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md).

```mermaid
flowchart LR
    D[DETECT] --> I[ISOLATE]
    I --> G[DEGRADE]
    G --> R[RECOVER]
    R --> V[VERIFY]
```

## Observability Model

```mermaid
flowchart TD
    D[DEVICE] --> Z[ROOM / ZONE]
    Z --> B[BUILDING]
    B --> F[FACILITY]
    F --> DI[DISTRICT]
    DI --> C[CITY]

    D --> O[OBSERVATORY]
    Z --> O
    B --> O
    F --> O
    DI --> O
    C --> O

    O --> SS[SYSTEM STATE]
    SS --> W[WATCHDOG]
    W --> FD[FAILURE DETECTION]
    FD --> RC[RECOVERY]
```

Observability is a state-construction mechanism, not only a dashboard.

## Evidence and Claim Discipline

Full model: [architecture/evidence/EVIDENCE_MODEL.md](architecture/evidence/EVIDENCE_MODEL.md).

Allowed Maturity Status values (never mixed with Artifact Type values such as POLICY, PLACEHOLDER, FLAGSHIP ARCHITECTURE):

- CONCEPT
- HYPOTHESIS
- DESIGN
- IMPLEMENTATION
- EXPERIMENT
- MEASURED
- VERIFIED
- [UNRESOLVED_SPEC: Requires Hardware/Code Verification]

Epistemic hierarchy:

```mermaid
flowchart TD
    I[IDEA] --> C[CONCEPT]
    C --> H[HYPOTHESIS]
    H --> D[DESIGN]
    D --> IM[IMPLEMENTATION]
    IM --> EX[EXPERIMENT]
    EX --> M[MEASUREMENT]
    M --> E[EVIDENCE]
    E --> VR[VALIDATED RESULT]
    VR --> EK[ENGINEERING KNOWLEDGE]
```

## Navigation

- Canonical terminology: docs/foundations/TERMINOLOGY.md
- Foundations: docs/foundations/
- System architecture: architecture/
- Layer contracts: architecture/LAYER_CONTRACTS.md
- AI authority contract: architecture/security/AI_AUTHORITY_CONTRACT.md
- Threat model: architecture/security/THREAT_MODEL.md
- Failure/recovery model: architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md
- Evidence model: architecture/evidence/EVIDENCE_MODEL.md
- Traceability: architecture/TRACEABILITY.md
- Consolidated cross-subsystem map and audit: architecture/SOVEREIGN_ENGINEERING_MAP.md
- Machine-readable schemas: schemas/
- Flagship: projects/ericaos/
- Case studies: case-studies/
- Evidence artifacts: evidence/, measurements/, experiments/
- Matrix: COMPETENCY_EVIDENCE_MATRIX.md
