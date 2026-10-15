# 🦉 OHardn

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OHardn** — Linux Host Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

Linux host hardening auditor (CIS-style sysctl, users, sudo, filesystem, services)

---

## ✨ Features

- Kernel / sysctl auditor — live /proc/sys values vs persisted /etc/sysctl.conf + sysctl.d drop-ins, drift detection, recommended values per key
- User & authentication auditor — extra UID 0 accounts, empty / unlocked passwords (shadow only when readable), world-writable homes, login.defs password ageing, PAM password-quality hints
- Sudoers parser — includes / includedir, aliases, NOPASSWD, !authenticate, broad ALL=(ALL) ALL grants to non-admin principals, env_keep / secure_path
- Filesystem auditor — world-writable dirs outside tmp, SUID / SGID inventory with known-risky (GTFOBins- style) binaries, /tmp sticky bit, critical file permissions (/etc/passwd, shadow, group, gshadow)
- Services & timers — enabled systemd units with an allowlist; flags legacy / risky daemons
- Network exposure summary — listening TCP/UDP via ss, netstat or /proc/net fallback
- Weighted 0–100 score, A–F grade, per-category subscores and remediation text per finding
- Baseline snapshots (JSON) + regression diff
- Export TXT / MD / JSON / CSV with save chooser, clipboard copy, --suggest sysctl snippet writer
- Full CLI mode (--all, --sysctl, --json, --fail-on)

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OHardn
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
