# Portable ARM64 Engineering Workstation

Artifact Type: PROJECT
Maturity Status: MIXED (see Runtime State Matrix)
Operational State: ACTIVE ENGINEERING ENVIRONMENT (private device, not in this public repository)
Public Repository Presence: This document only. No package lists, backups, or binaries have been imported into this repository.

Scope:

- ARM64 Linux base
- local development and operations
- service supervision
- offline-first workflow
- secure private access

## Evidence Basis and Its Limits

Two tiers of evidence exist for this device class, and they are not equivalent:

1. **FILE-VERIFIED**: real audit output files were directly opened and read by the assistant (Termux `tools_capability_report.txt` and `network_audit_report.txt`, dated 26 Aug 2026). These confirm, on an actual Android/Termux device: ADB 1.0.41 operational, Nmap 7.991 executed a real scan of localhost (100 ports, all closed/filtered, 0 open), OpenSSH 10.5p1 present, `dos2unix`/`patch`/`cmatrix`/`dialog`/`sudo` present, no open network sockets found by `lsof` at capture time.
2. **SELF-REPORTED (raw transcript)**: a separate, more extensive terminal transcript was supplied listing Termux `$PREFIX/bin` (172 packages) and a nested `proot-distro` Debian GNU/Linux 13 environment (512 packages), including full executable listings. This is raw command+output text, not a file located and opened by the assistant in this workspace, so it is one evidence tier below FILE-VERIFIED — but it is stronger than a narrative description because it includes explicit negative checks (see below), and it is internally consistent with the FILE-VERIFIED tier above.

## Confirmed Negative Findings (from the SELF-REPORTED transcript)

The supplied transcript explicitly ran presence/absence checks, not just inventory listings. At capture time, in **both** Termux and the nested Debian environment:

- `ps -ef | grep -E 'sshd|nginx|named|suricata|llama|erica|headscale|tailscale|python'` matched no daemon process (only the interactive shell itself).
- `ss -lntup` returned no listening TCP/UDP sockets.

This means: `headscale`, `tailscale`/`tailscaled`, `nginx`, `sshd`, `named`, `suricata`, and any local `llama`-based inference server were **installed and executable but not running** on this device at capture time. Do not describe any of these as an active service on this device.

**Cross-environment PATH coupling — confirmed by transcript, not yet assessed for risk**: the transcript shows Termux's `$PATH` as `/data/data/com.termux/files/home/go/bin:/data/data/com.termux/files/usr/bin`, and a check inside the nested Debian environment (`proot-distro login debian -- ... echo $PATH`) shows `/data/data/com.termux/files/usr/bin` also present in Debian's `PATH`. This is a real, self-reported observation, not a narrative claim — but whether it is intentional integration or an isolation weakness requires a controlled test, not inference from an inventory listing.

Distinguish, per component:

- **Installed** — a package/binary is present.
- **Executable** — the binary is runnable.
- **Configured** — a config file exists.
- **Running** — an active process was observed.
- **Listening** — an open socket was observed.
- **Tested** — an explicit test/invocation was performed.
- **Verified** — independently confirmed by inspection (FILE-VERIFIED) or a linked Evidence record.

## Runtime State Matrix (grouped by function)

| Function Group | Representative Tools | Installed | Executable | Running/Listening | Verification Level |
|---|---|---|---|---|---|
| Android host + Termux ARM64 userspace | Termux base (172 packages), `proot-distro` | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Android diagnostics (separate capture) | ADB 1.0.41, Nmap 7.991 (localhost scan executed), OpenSSH 10.5p1 | Yes | Yes, scan actually run | No open ports found | FILE-VERIFIED |
| Nested Debian environment | Debian GNU/Linux 13 (trixie), 512 packages under PRoot | Yes | Yes | Userspace only, no PID 1 claim made | SELF-REPORTED (raw transcript) |
| ARM64 native toolchain | clang-21/LLVM, `aarch64-linux-android-*`, `aarch64-linux-gnu-gcc-14`, gdb, make, cmake, nasm | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Binary/reverse-engineering toolchain | radare2 family, objdump, readelf, strings | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Network diagnostics | ip, ss, tcpdump, tshark, mtr, dig, nmap | Yes | Yes | Confirmed idle at capture time | SELF-REPORTED (raw transcript) + FILE-VERIFIED (localhost scan) |
| Security/web testing tooling | nuclei, ffuf, httpx, subfinder, sqlmap, hydra | Yes | Yes | Not running | SELF-REPORTED (raw transcript) |
| DNS/DNSSEC toolchain | `named`, `dnssec-*`, `rndc` | Yes | Yes | Confirmed NOT running/listening | SELF-REPORTED (raw transcript) |
| Web server | nginx | Yes | Yes | Confirmed NOT running/listening | SELF-REPORTED (raw transcript) |
| Remote engineering (SSH) | ssh, sshd, ssh-keygen | Yes | Yes | Confirmed NOT running/listening | SELF-REPORTED (raw transcript) |
| Sovereign mesh tooling | headscale, tailscale, tailscaled | Yes | Yes | Confirmed NOT running/listening | SELF-REPORTED (raw transcript) |
| Local AI (llama-server/GGUF) on this device | llama, erica (grepped for, not found) | Not confirmed present | N/A | Confirmed NOT running | SELF-REPORTED (raw transcript, negative result) |
| System/process/namespace tooling | proot, unshare, nsenter, systemd analysis tools | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Android bridge | adb, fastboot, logcat, getprop | Yes | Yes, `adb` actually invoked | Daemon started successfully | FILE-VERIFIED |
| File/data engineering | tar, zip, jq, sed, awk, openssl | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Python runtime | Python 3.13/3.14, pip, Flask | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Go security binaries | ffuf, httpx, nuclei, subfinder (`$HOME/go/bin`) | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Rust toolchain | rustup (`/root/.cargo/bin`) | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Smart-contract security (Debian) | solc, slither, crytic-compile | Yes | Yes | N/A | SELF-REPORTED (raw transcript) |
| Network security/IDS | suricata + related tooling | Yes | Yes | Confirmed NOT running | SELF-REPORTED (raw transcript) |

`[UNRESOLVED_SPEC: Requires Hardware/Code Verification]` applies specifically to: exact package versions, exact benchmark/performance figures, thermal limits, and a security determination on the PATH coupling finding above — direct testing is required before any security conclusion is drawn.

## Reproducibility

Public Reproducibility: None. No scripts, configuration, or package manifests from this environment have been published in this repository.
