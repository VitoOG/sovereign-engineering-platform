# Security Engineering — DevSecOps / IT-OT Assurance

Artifact Type: CROSS-CUTTING ENGINEERING CAPABILITY

Project Status: MIXED MATURITY

Maturity Status: MIXED — architecture, host hardening, scoped diagnostics, and private validation activities exist across separate workstreams; no single integrated security product is claimed

Public Repository Status: SANITIZED PRACTICE / ARCHITECTURE PROFILE

## System Role

Security engineering is a cross-cutting assurance capability applied to the workstation, edge, network, software supply chain, AI tools, and cyber-physical systems.

It is not a separate business or a single security product. It provides security requirements, threat modelling, trust-boundary analysis, hardening, scoped assessment, reproducible validation, and evidence packaging across projects.

## Scope

- Linux host and service hardening.
- Network segmentation, identity, remote-access boundaries, and least privilege.
- DevSecOps and source/configuration review.
- Software supply-chain and dependency analysis.
- AI/agent capability and tool-permission assessment.
- IT/OT boundary analysis and control-path isolation.
- Authorised vulnerability research and reproducible proof-of-concept validation.
- Evidence handling, remediation tracking, and recovery verification.

## Engineering Rules

1. Authorization and scope are established before testing.
2. Passive inspection precedes active validation where practical.
3. Test only owned assets or explicitly authorized targets.
4. Tool availability is not proof of execution permission or network reachability.
5. Reproduction must be bounded, reversible, and evidence-backed.
6. Findings distinguish confirmed behaviour, suspected causes, impact hypotheses, and unresolved conditions.
7. Sensitive customer, program, credential, and exploit details remain private unless disclosure is explicitly approved.
8. Physical control authority remains deterministic and independently protected.

## Evidence and Maturity

This SEP repository contains public threat-model and AI-authority architecture documents. It does not contain an integrated security operations platform or a complete automated control environment.

Separate private security-research and validation workstreams have produced source-level reviews, reproducible test packages, and evidence artefacts. They are not reproduced here, and this profile makes no target-specific vulnerability, customer, reward, or remediation claim.

## Integration Relationships

- [Sovereign Mesh](../sovereign-mesh/README.md): network identity and access path.
- [Portable ARM64 Workstation](../arm64-workstation/README.md): portable security/diagnostic tool environment.
- [ERICA OS](../ericaos/README.md): agent capability, task, and policy boundaries.
- [Deterministic Controller](../deterministic-controller/README.md): physical authority and safety boundary.
- [Golden Greens](../golden-greens/README.md): CEA/OT security and process-integrity concerns.

## Next Verification Gates

1. Maintain per-project threat models and asset/scope records.
2. Link each security assertion to source, reproduction procedure, or measured evidence.
3. Validate host isolation, network paths, permissions, and service exposure from actual runtime state.
4. Establish an IT/OT interface and trust-zone review checklist.
5. Track remediation through testable acceptance criteria and regression checks.
6. Publish only sanitized, explicitly disclosable findings.

This profile does not imply certification, conformity assessment, legal advice, or authorization to test third-party systems.
