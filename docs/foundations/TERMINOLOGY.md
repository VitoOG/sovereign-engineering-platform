# Canonical Terminology

Artifact Type: SPEC
Maturity Status: DESIGN

This document is the single source of truth for terminology used across this repository. Where other documents define these terms informally, this document takes precedence. Informal restatements elsewhere must be summaries only, not alternate definitions.

Each term includes: Definition, Scope, Producer, Consumer, Relationship to adjacent terms.

---

## Observation

1. Definition: A single act of perceiving physical or system reality through a sensor, log, or monitoring mechanism.
2. Scope: Applies at any layer (L0-L6) where reality is sampled.
3. Producer: Sensors, agents, monitoring probes, human reporters.
4. Consumer: Acquisition stage, Observatory.
5. Relationship: An Observation, once captured and transmitted, becomes Sensor Telemetry. Observation is the act; telemetry is the transmitted record of it.

## Sensor Telemetry

1. Definition: Raw, unvalidated data emitted directly by a physical sensor or hardware interface.
2. Scope: L0/L1 boundary, immediately after Observation.
3. Producer: Sensors, embedded acquisition firmware.
4. Consumer: Acquisition stage.
5. Relationship: Input to Acquisition. Precedes Validation. Distinct from Control Telemetry (which reflects control decisions, not raw physical readings).

## Control Telemetry

1. Definition: Data describing the internal state, decisions, and transitions of the deterministic control layer (e.g., FSM state, active policy, control-loop timing).
2. Scope: L1/L2, emitted by the deterministic control component.
3. Producer: Deterministic Control.
4. Consumer: Observatory, Knowledge layer, Watchdog.
5. Relationship: Distinct from Sensor Telemetry (raw input) and Actuator Command Telemetry (issued commands). Describes the controller's own behavior.

## Feedback Telemetry

1. Definition: Data reporting the observed physical result of an actuation, used to confirm or refute expected system response.
2. Scope: L0/L1, emitted after Actuation and re-observed via Sensors.
3. Producer: Sensors observing post-actuation physical state.
4. Consumer: State Estimation, Deterministic Control (closed loop), Observatory.
5. Relationship: Closes the control loop. Distinct from Actuator Feedback Telemetry (device-level actuator status) by being physical-outcome telemetry rather than device-status telemetry.

## Event

1. Definition: A discrete, timestamped occurrence of interest derived from telemetry, state change, or system behavior (e.g., threshold crossed, fault detected, policy denied).
2. Scope: Any layer; consumed primarily by Observatory and Watchdog.
3. Producer: Validation, Deterministic Control, Watchdog, Policy Engine.
4. Consumer: Observatory, Knowledge layer, Recovery workflow.
5. Relationship: Derived from one or more telemetry streams or state transitions. Not raw telemetry; always the product of interpretation.

## State

1. Definition: The explicit, current representation of a system or subsystem's condition, ownership-tracked by exactly one component.
2. Scope: Any layer; each layer owns its own state per Layer Contracts.
3. Producer: State Estimation (derived state), or explicit owning component.
4. Consumer: Deterministic Control, Watchdog, Intelligence layer (read-only), Observatory.
5. Relationship: State is authoritative; State Estimate is a computed approximation used when direct state is not observable.

## State Estimate

1. Definition: A computed or inferred approximation of State when direct measurement is unavailable or noisy, produced through validated fusion of telemetry.
2. Scope: L2-L4, wherever direct state observation is incomplete.
3. Producer: State Estimation function/component.
4. Consumer: Deterministic Control, Intelligence layer.
5. Relationship: Subordinate to State when both exist; must be explicitly labeled as an estimate, never conflated with directly observed State.

## Policy

1. Definition: A declared, versioned rule set that governs what actions are permitted, denied, or require approval for a given actor and context.
2. Scope: Cross-layer; enforced primarily at L3-L5 boundary before any Command reaches Deterministic Control.
3. Producer: Human authority, Policy Engine configuration process.
4. Consumer: Policy Engine (evaluates), Deterministic Control (receives decision).
5. Relationship: Governs Authority and gates Command approval. Distinct from Authority (a policy defines what authority means for a given actor/action pair).

## Authority

1. Definition: The scope of actions an actor (Human, AI, Agent, Robot) is permitted to request or execute, as determined by Policy.
2. Scope: Cross-layer; evaluated per actor and per capability.
3. Producer: Policy Engine (assigns/evaluates authority per policy).
4. Consumer: Capability Resolution, Deterministic Executor.
5. Relationship: Authority is an evaluated property (per actor), while Policy is the rule definition that produces it.

## Capability

1. Definition: An atomic, named operation contract that an actor can request (e.g., file.read, macro.execute).
2. Scope: Cross-layer; defined in the capability system.
3. Producer: System/agent designers register capabilities.
4. Consumer: Capability Resolution step in the AI Authority Contract.
5. Relationship: A Command is a specific invocation of a Capability with bound parameters. Capability is the contract; Command is the instance.

## Command

1. Definition: A specific, parameterized instruction requesting execution of a Capability, submitted for policy evaluation.
2. Scope: Cross-layer; flows from Capability Resolution to Policy Validation to Deterministic Executor.
3. Producer: Human, AI, Agent (as requester).
4. Consumer: Policy Engine (validates), Deterministic Executor (executes if approved).
5. Relationship: Becomes an Approved Command only after Policy Validation returns ALLOW. Execution follows only from an Approved Command.

## Execution

1. Definition: The act of carrying out an Approved Command by a Deterministic Executor, producing an effect (actuation, file change, workflow step).
2. Scope: L1-L2 for physical actuation; any layer for digital operations.
3. Producer: Deterministic Executor, Firmware, Macro runtime.
4. Consumer: Actuator, downstream system state.
5. Relationship: Always preceded by Policy Validation and an Approved Command. Produces Evidence via Verification.

## Verification

1. Definition: The act of checking whether an Execution produced the expected, safe, and policy-conformant result.
2. Scope: Immediately following Execution, at the same or a supervising layer.
3. Producer: Deterministic Controller, Watchdog, test harness.
4. Consumer: Evidence record, Recovery workflow (if verification fails).
5. Relationship: Verification failure triggers Recovery (Detect stage). Verification success produces Evidence supporting a Validated Result.

## Evidence

1. Definition: A traceable, provenance-tagged artifact that substantiates a claim, measurement, test result, or execution outcome.
2. Scope: Cross-layer; stored under evidence/, measurements/, experiments/, tests/.
3. Producer: Verification, Measurement, test execution.
4. Consumer: Evidence Model, Competency Evidence Matrix, engineering decisions.
5. Relationship: Evidence is required to move a claim from EXPERIMENT to MEASURED to VERIFIED in the Evidence Model lifecycle.

## Recovery

1. Definition: The defined workflow that returns a system from a detected failure or degraded state to a safe or nominal operating state.
2. Scope: Any layer; formalized in the Failure and Recovery Model.
3. Producer: Watchdog, Deterministic Control, human operator (for escalated cases).
4. Consumer: Affected layer, Observatory (records recovery event), Evidence.
5. Relationship: Follows Detect -> Isolate -> Degrade -> Recover -> Verify. Distinct from Deployment (which introduces change, not restores prior state).

## Deployment

1. Definition: The controlled introduction of a validated engineering change into an operating system.
2. Scope: L2-L6; part of the Engineering Evolution loop.
3. Producer: Engineering change process, following Validation.
4. Consumer: Updated system, subsequent Telemetry generation.
5. Relationship: Distinct from Recovery (Deployment introduces new validated behavior; Recovery restores known-good behavior).

## Measurement

1. Definition: A quantified observation recorded under a defined method, producing a numeric or categorical value with stated precision and conditions.
2. Scope: Applies wherever an Experiment or test produces quantified output.
3. Producer: Test harness, instrumentation, experiment protocol.
4. Consumer: Evidence record, Evidence Model maturity classification.
5. Relationship: A Measurement is one type of Evidence input; not all Evidence is a Measurement (e.g., a passed conformance test is Evidence but may not be a Measurement).

## Provenance

1. Definition: The recorded origin, method, and chain of custody of a piece of Data, Evidence, or Knowledge.
2. Scope: Cross-layer; mandatory for any Evidence or Knowledge artifact.
3. Producer: Whatever component originates or transforms the artifact (must record itself as a provenance step).
4. Consumer: Knowledge layer, Evidence Model, audit processes.
5. Relationship: Provenance is metadata attached to Evidence/Knowledge; it is not itself a lifecycle stage.

## Decision

1. Definition: A determination made by a human, policy engine, or deterministic controller that selects one course of action among alternatives.
2. Scope: Cross-layer; includes Policy Decisions (ALLOW/DENY/REQUIRE_APPROVAL) and Engineering Decisions.
3. Producer: Policy Engine, Human authority, Deterministic Control (bounded decisions only).
4. Consumer: Command approval path, Engineering Evolution loop.
5. Relationship: A Policy Decision gates whether a Command becomes an Approved Command. An Engineering Decision gates whether a Deployment proceeds.

## Actuation

1. Definition: The physical effect produced by an Actuator executing an Approved Command via a Deterministic Executor.
2. Scope: L0/L1 boundary; the terminal step of the CPS control loop before the physical world changes.
3. Producer: Actuator hardware.
4. Consumer: Physical World (state changes), subsequently re-observed via Sensors (Feedback Telemetry).
5. Relationship: Always the last step of Execution when the Command targets physical hardware. Never triggered directly by AI without passing through Policy Validation and Deterministic Executor.

---

## Non-Overlap Rules

- Telemetry is always raw or near-raw signal data tied to a specific stage (Sensor/Control/Feedback/etc.); an Event is always a derived interpretation.
- State is authoritative; State Estimate is explicitly approximate and must never be silently substituted for State in a safety-critical path.
- Policy defines rules; Authority is the evaluated permission derived from Policy for a specific actor.
- Command is a request; Execution is the act; Actuation is the physical-world subset of Execution.
- Evidence is the general category; Measurement and Provenance are properties/subtypes of Evidence, not synonyms for it.
- Recovery restores known-good state; Deployment introduces new validated state. They must never be used interchangeably.
