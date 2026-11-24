# 🦉 OHardn

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OHardn** — Linux Host Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OHardn — Linux Host Hardening Auditor. It provides kernel / sysctl auditor — live /proc/sys values vs persisted /etc/sysctl.conf + sysctl.d drop-ins, drift detection, recommended values per key. Operators can export results (including machine-readable formats) and gate CI with severity thresholds where supported.

---

## ✨ Features

- Kernel / sysctl auditor — live /proc/sys values vs persisted /etc/sysctl.conf + sysctl.d drop-ins, drift detection, recommended values per key
- User & authentication auditor — extra UID 0 accounts, empty / unlocked passwords (shadow only when readable), world-writable homes, login.defs password ageing, PAM password-quality hints
- Sudoers parser — includes / includedir, aliases, NOPASSWD, !authenticate, broad ALL=(ALL) ALL grants to non-admin principals, env_keep / secure_path
- Filesystem auditor — world-writable dirs outside tmp, SUID / SGID inventory with known-risky (GTFOBins- style) binaries, /tmp sticky bit, critical file permissions (/etc/passwd, shadow, group, gshadow)
- Services & timers — enabled systemd units with an allowlist; flags legacy / risky daemons
- Network exposure summary — listening TCP/UDP via ss, netstat or /proc/net fallback

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OHardn                                     # interactive menu
./OHardn --json -o report.json
./OHardn --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OHardn --help   # watch every network call
firejail --net=none ./OHardn --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
