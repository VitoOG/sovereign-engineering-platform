# CASE-002: ERICAOS Local AI Runtime

Artifact Type: CASE STUDY
Maturity: MIXED (see component table in [projects/ericaos/README.md](../../projects/ericaos/README.md))

A local inference runtime, agent orchestration code, and edge/service supervision exist and have been file-verified in a private engineering environment (not in this public repository). The AI-to-actuation authority/policy path described below remains DESIGN-level and unimplemented, in either environment. This case study does not claim PARTIAL IMPLEMENTATION of the public repository.

1. Problem: Need local intelligence that supports engineering decisions without ceding control authority.
2. Context: LLM utility is high, but nondeterminism and hallucination risk require strict boundaries.
3. Requirements: Local model runtime, RAG grounding, policy-gated action path.
4. Constraints: Compute limits, model quality, provenance quality.
5. Threat Model: Prompt injection, unsafe tool use, policy bypass. See [architecture/security/THREAT_MODEL.md](../../architecture/security/THREAT_MODEL.md).
6. Architecture: AI as recommendation/orchestration layer above deterministic control. See [architecture/LAYER_CONTRACTS.md](../../architecture/LAYER_CONTRACTS.md#l5-intelligence).
7. Design: [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md) defines the authorization path (DESIGN maturity, unimplemented in any environment).
8. Implementation: A local inference runtime (llama-server + Qwen2.5-0.5B GGUF), agent orchestration code (CoreAgent), and systemd service supervision are IMPLEMENTED and file-verified in a private engineering environment. None of this exists in this public repository. See component table in [projects/ericaos/README.md](../../projects/ericaos/README.md).
9. Tests: Automated tests exist and have been executed in the private engineering environment (pytest files plus a populated pytest cache confirming prior runs). Policy-conformance and unsafe-action rejection tests for the authority path specifically are NOT IMPLEMENTED in either environment.
10. Measurements: NOT IMPLEMENTED — no quantified, reproducible measurement exists in either environment.
11. Failures: NOT IMPLEMENTED — no recorded failure/incident data was inspected.
12. Recovery: Intended fallback to deterministic workflows and human approval per [architecture/security/AI_AUTHORITY_CONTRACT.md](../../architecture/security/AI_AUTHORITY_CONTRACT.md); not implemented in either environment.
13. Evidence: File-level inspection performed by the assistant (not a formal Evidence record). No Evidence record conforming to [schemas/evidence.schema.json](../../schemas/evidence.schema.json) exists in this repository's evidence/ directory.
14. Limitations: No verified runtime metrics exist.
15. Lessons: Authority separation must be designed before any runtime is built.
16. Next Iteration: Implement a minimal Policy Engine and Deterministic Executor stub, then add a conformance test suite.
17. Maturity: CONCEPT
