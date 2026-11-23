# ERICA Swarm — Historical Agent-Orchestration Candidate

Artifact Type: ERICA OS COMPONENT CANDIDATE

Project Status: ARCHITECTURE

Maturity Status: DESIGN / EXPERIMENTAL (integration and execution authority unresolved)

Public Repository Status: ARCHITECTURE / SOURCE-RECONSTRUCTION SUMMARY

## System Role

ERICA Swarm is a historical agent-orchestration and task-delegation candidate associated with the ERICA OS development line.

It is not a second ERICA OS, not a replacement for the deterministic Go workflow, and not an independently verified autonomous agent runtime.

## Historical Findings

The 2026-11-13 source review described a separate JSON-backed mission/task/agent/artifact state model in the Swarm environment.

A Python-to-Swarm adapter was identified as an optional advisory planner path:

- It is selected only through a specific planner-backend configuration branch.
- The reviewed configuration did not enable that branch by default.
- The adapter calls an advisory endpoint; it does not transfer task ownership or workflow authority.
- Python TaskStore remains a separate task owner in the historical design.
- The Go ERICA OS target did not contain a verified Swarm bridge in that inventory.

The provisional disposition for the Swarm candidate and the Core-to-Swarm adapter was REFERENCE, pending a decision about advisory versus workflow responsibilities and a security/contract review.

## Authority Boundary

The model/agent may propose analysis, plans, or structured outputs. It does not receive workflow ownership, approval authority, filesystem authority, or physical-control authority merely by returning a response.

The following remain distinct:

- ERICA task/workflow state.
- Swarm mission/task/agent/artifact state.
- Model inference requests and responses.
- Capability grants and execution authority.
- Human approval and deterministic runtime policy.

No cross-store transaction, shared task identity contract, or fully integrated orchestration path is claimed.

## Next Verification Gates

1. Locate the canonical Swarm source tree and exact revision.
2. Reconstruct the separate mission/task schemas and their state owners.
3. Inspect service endpoints, authentication, tool permissions, logs, stop behaviour, and filesystem/network effects.
4. Determine whether the adapter is purely advisory or performs any stateful action.
5. Define a versioned contract before considering integration.
6. Preserve the deterministic ERICA workflow as the authority unless an explicit architecture decision changes that boundary.

## Relationship

This profile is linked under [ERICA OS](../ericaos/README.md) as a component lineage record. It is not a separate flagship product or evidence of a running swarm.
