# Security Architecture

Artifact Type: SPEC
Maturity Status: DESIGN

Canonical documents (authoritative, do not re-derive):

- Threat model: [architecture/security/THREAT_MODEL.md](THREAT_MODEL.md)
- AI authority contract: [architecture/security/AI_AUTHORITY_CONTRACT.md](AI_AUTHORITY_CONTRACT.md)

Security chain summary:

Identity -> Authentication -> Authorization -> Policy -> Execution -> Audit -> Evidence

Scope includes threat modeling, trust boundaries, least privilege, cryptographic identity, secrets and key management, supply-chain considerations, incident detection and recovery. No implementation or enforcement currently exists in this repository.
