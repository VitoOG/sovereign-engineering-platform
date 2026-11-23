# ERICA Model Routing and Specialist Runtime

Artifact Type: ERICA OS SUBSYSTEM PROFILE

Project Status: MIXED MATURITY

Maturity Status: MIXED — historical configuration/runtime evidence exists; canonical routing and current execution paths remain unresolved

Parent Platform: [ERICA OS](../ericaos/README.md)

Public Repository Status: ARCHITECTURE / HISTORICAL LINEAGE SUMMARY

## System Role

This profile isolates the AI/ML and model-orchestration capability within ERICA OS from the wider platform and from individual model runtimes.

The subsystem is responsible for selecting a suitable model or worker for a task, preserving provider/model identity, routing policy, resource limits, fallbacks, and provenance. It is not a chatbot UI and is not a standalone platform.

## Distinct Responsibilities

| Capability | Responsibility | Boundary |
|---|---|---|
| Model registry | Canonical identity, provider, weight digest, quantization, context and resource requirements | An alias is not proof of distinct model weights |
| Task router | Map task classes and constraints to approved workers | Historical CANON routing concept must be recovered from actual config/code |
| Local inference | Serve local model weights through a runtime such as llama.cpp or Ollama | Inference runtime does not own task/workflow authority |
| Specialist workers | Bounded roles such as coding, planning, extraction, or classification | Model role is not a permission grant |
| Orchestration | Delegate bounded tasks, collect results, track state and retries | Separate from model inference and physical actuation |
| Policy boundary | Validate tools, capabilities, budgets, and proposed actions | Prompts alone do not enforce permissions |

## Historical Evidence and Limits

The historical ERICA reconstruction records:

- A canonical task-to-model routing concept, described as selecting different specialist models for different task types.
- Historical configuration roles such as `model`, `planner_model`, `chat_model`, and `deep_chat_model`.
- Model aliases including `erica-fast:latest` and `erica-os:latest`, whose underlying weights and Modelfiles require identity reconciliation.
- Historical local runtime observations for llama-server and Ollama on different machines.
- A mobile llama.cpp inference experiment that returned a bounded 128-token response and was classified as partial inference verification.

These are generation-specific historical observations. They do not establish that canonical routing is currently configured, that all workers run concurrently, or that the current Go target has an integrated router.

## Relationship to Other ERICA Components

- [ERICA OS](../ericaos/README.md) owns project context, workflow state, policy, and overall runtime boundaries.
- [ERICA Swarm](../erica-swarm/README.md) is a historical agent-orchestration candidate with a distinct mission/task state model; it is not interchangeable with the model router.
- [ERICA Library](../erica-library/README.md) provides source-grounded retrieval; retrieval is an input capability, not a router.
- The deterministic controller remains the only authority for critical physical actuation.

## Next Verification Gates

1. Recover the authoritative CANON routing schema and task taxonomy.
2. Pin router code/config revisions and map actual call paths.
3. Reconcile aliases against model manifests, Modelfiles, and weight digests.
4. Separate model selection, inference transport, orchestration, tool permissions, and workflow state.
5. Test fallback, timeout, resource-budget, unavailable-provider, and malformed-output behaviour.
6. Verify that no model output bypasses policy validation or deterministic control.

No current multi-model production routing, simultaneous specialist swarm, or autonomous actuation capability is claimed.
