# CASE-001: Portable ARM64 Engineering Workstation

Artifact Type: CASE STUDY
Maturity: CONCEPT (public repository); component evidence exists privately — see [projects/arm64-workstation/README.md](../../projects/arm64-workstation/README.md)

1. Problem: Need portable sovereign engineering environment for field and edge operations.
2. Context: Cloud dependence creates fragility and latency for critical workflows.
3. Requirements: ARM64 Linux, local tooling, offline-first operation, secure remote management.
4. Constraints: Power, thermal limits, hardware availability, OS compatibility.
5. Threat Model: Device compromise, credential theft, untrusted networks. See [architecture/security/THREAT_MODEL.md](../../architecture/security/THREAT_MODEL.md).
6. Architecture: Local-first workstation with private network access and service supervision. See [architecture/edge/README.md](../../architecture/edge/README.md).
7. Design: NOT IMPLEMENTED — no design document beyond this case study exists yet.
8. Implementation: IMPLEMENTED — PRIVATE. A real Android/Termux device with a nested Debian 13 (PRoot) environment exists, carrying ARM64 native toolchains, network diagnostics, and security tooling. Not exported to this repository.
9. Tests: TEST-VERIFIED for one item only — a real Nmap scan of localhost was executed and its output inspected (100 ports scanned, 0 open). All other tool presence is SELF-REPORTED (raw transcript) or FILE-VERIFIED (existence of the audit report file), not a tested capability.
10. Measurements: NOT IMPLEMENTED — no benchmark or performance figures were captured.
11. Failures: NOT OBSERVED — explicit checks found no running sshd, nginx, named, suricata, headscale, tailscaled, or llama-based process, and no listening sockets, at capture time.
12. Recovery: Intended to follow [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md); not implemented as a tested procedure.
13. Evidence: Two real audit files were opened and read directly by the assistant (FILE-VERIFIED); a further raw terminal transcript was supplied and assessed as SELF-REPORTED (not independently re-executed, no matching file located). No linked artifact exists under this repository's evidence/, measurements/, or tests/.
14. Limitations: No verified benchmark or field performance report exists in this repository. A cross-environment PATH coupling (Termux binaries visible from the nested Debian PATH) was observed in the transcript and flagged for architectural review — it is not evaluated as a vulnerability without a controlled test.
15. Lessons: Portability must not reduce determinism; installed-and-executable must never be conflated with running-and-verified.
16. Next Iteration: Run a controlled, repeatable capability test (not just an inventory dump) and persist its output as a linked Evidence record conforming to [schemas/evidence.schema.json](../../schemas/evidence.schema.json).
17. Maturity: CONCEPT (public repository)
