# Sovereign Mesh / Private Infrastructure

Artifact Type: PROJECT

Maturity Status: MIXED MATURITY

Implementation Status:
IMPLEMENTED COMPONENTS — PRIVATE (tooling installed only; no running mesh observed)

Public Repository Status:
SANITIZED EVIDENCE / ARCHITECTURE

## System Scope

Private network architecture for resilient edge operations with identity-aware access and constrained management paths. See [architecture/network/README.md](../../architecture/network/README.md).

## Implemented Components

| Component | Status | Evidence |
|---|---|---|
| Headscale, Tailscale, `tailscaled` binaries | IMPLEMENTED — PRIVATE (installed/executable only) | SELF-REPORTED (raw terminal transcript: binaries present in both a Termux and a nested Debian environment) |
| `tailscaled.service` unit-enabled state (separate Raspberry Pi host) | IMPLEMENTED — PRIVATE (enabled state only) | FILE-VERIFIED (`systemctl list-unit-files` output opened and read directly) |
| SSH client/server binaries (`ssh`, `sshd`) | IMPLEMENTED — PRIVATE (installed/executable only) | SELF-REPORTED (raw transcript) |

## Architecture Components

| Component | Status | Evidence |
|---|---|---|
| WireGuard/mesh architecture | ARCHITECTURE | [architecture/network/README.md](../../architecture/network/README.md) trust-zone diagram |
| Segmentation model | ARCHITECTURE | Same document |
| Identity-aware access | ARCHITECTURE (not tested) | Same document |
| Local supervision | IMPLEMENTED — PRIVATE if the unit-enabled state above counts; no supervision *logic* code was inspected | See Implemented Components above |
| Production sovereign mesh | NOT VERIFIED | Explicit `ps`/`ss` checks in the supplied transcript found **no running mesh process and no listening socket** in either the Termux or nested Debian environment at capture time |

## Evidence

A real unit-file listing and a raw terminal transcript (with explicit negative process/socket checks) were the evidentiary basis; no mesh configuration file, key, or ACL was found or inspected anywhere. Full detail: [case-studies/CASE-004/README.md](../../case-studies/CASE-004/README.md).

## Verification Boundaries

"Enabled" (systemd) and "installed" (package presence) are not equivalent to "running"; neither was observed for any mesh component in this session. Do not describe a running/active mesh anywhere in this project.

## Known Gaps

Headscale version, listen address, private key path, database path, and unix socket path referenced in an external private document remain SELF-REPORTED/CLAIMED, not independently verified — see [architecture/SOVEREIGN_ENGINEERING_MAP.md](../../architecture/SOVEREIGN_ENGINEERING_MAP.md).

## Reproducibility

Public Reproducibility: none.

## Public / Private Boundary

All tooling and unit-state evidence is private. No mesh secrets, keys, or configuration have been or should be copied into this repository.
