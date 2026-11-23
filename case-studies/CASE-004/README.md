# CASE-004: Sovereign Mesh / Private Infrastructure

Artifact Type: CASE STUDY
Maturity: MIXED MATURITY — mesh tooling IMPLEMENTED — PRIVATE (installed only, not running); production mesh NOT VERIFIED

1. Problem: Need secure private connectivity for distributed edge nodes.
2. Context: Public-cloud dependency and flat networking increase risk.
3. Requirements: WireGuard mesh, identity-aware access, segmentation.
4. Constraints: NAT environments, key lifecycle, node heterogeneity.
5. Threat Model: Unauthorized lateral movement, key leakage, management path exposure. See [architecture/security/THREAT_MODEL.md](../../architecture/security/THREAT_MODEL.md).
6. Architecture: Sovereign mesh with constrained access planes. See [architecture/network/README.md](../../architecture/network/README.md).
7. Design: NOT IMPLEMENTED — no node bootstrap or segmentation design document exists yet beyond this case study. A separate private architecture note explicitly records this as PROPOSED with no runtime wiring.
8. Implementation: Tooling is IMPLEMENTED — PRIVATE at the "installed" level only: `headscale`, `tailscale`, and `tailscaled` binaries were confirmed present and executable in a private Termux/Debian environment (SELF-REPORTED raw transcript), and a separate Raspberry Pi host lists `tailscaled.service` as `enabled` in `systemctl list-unit-files` (FILE-VERIFIED unit-state listing). No mesh configuration, node identity, or ACL file was found or inspected anywhere.
9. Tests: NOT IMPLEMENTED — segmentation policy tests and outage recovery drills are planned.
10. Measurements: NOT IMPLEMENTED.
11. Failures: NOT OBSERVED — explicit process and socket checks in the private Termux/Debian environment found no running `headscale`/`tailscaled` process and no listening socket at capture time. "Enabled" on the Raspberry Pi host does not establish it was running at any specific time; this was not independently checked.
12. Recovery: Key rotation, node quarantine, deterministic reconnect flows are intended per [architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md](../../architecture/reliability/FAILURE_AND_RECOVERY_MODEL.md); not implemented.
13. Evidence: A unit-file listing was opened and read directly (FILE-VERIFIED for enabled-state only); mesh tooling presence elsewhere is SELF-REPORTED (raw transcript). No mesh configuration file, key, or ACL was inspected. Specific values such as Headscale version, listen address, or custom SSH port remain SELF-REPORTED narrative claims from an external document, not independently verified.
14. Limitations: No production topology, running mesh process, or listening mesh socket has been observed anywhere in this audit.
15. Lessons: Connectivity must obey policy contracts; tool installation is not evidence of an active control plane.
16. Next Iteration: Produce a DESIGN document for node bootstrap and segmentation, then bring up one real mesh node and capture its running/listening state as linked Evidence.
17. Maturity: MIXED MATURITY (public repository remains ARCHITECTURE; see [projects/sovereign-mesh/README.md](../../projects/sovereign-mesh/README.md) for the component-level breakdown)
