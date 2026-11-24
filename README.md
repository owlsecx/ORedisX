# 🦉 ORedisX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OScan-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **ORedisX** — Redis / Valkey / KeyDB Configuration Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

ORedisX is an offline configuration auditor for Redis, Valkey and KeyDB. It parses redis.conf-style files with include chains and ACL rules, and flags network exposure, weak authentication, dangerous commands, TLS gaps and persistence-based write primitives. An optional safe probe performs only PING/INFO, never AUTH.

---

## ✨ Features

- Faithful redis.conf/valkey.conf/keydb.conf parser with include chains and per-directive origins
- ACL engine for inline and external rules (nopass, plaintext, over-privilege)
- Network-exposure analysis of bind, protected-mode and unix sockets
- Dangerous-command matrix (FLUSHALL, CONFIG, DEBUG, EVAL and more) with rename/ACL awareness
- TLS review and persistence write-primitive detection
- Optional safe PING/INFO probe, CWE/MITRE mapping and TXT/MD/JSON/CSV/SARIF export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ORedisX -c /etc/redis/redis.conf
./ORedisX --scan --root /mnt/collected --sarif -o report.sarif
./ORedisX --probe 127.0.0.1:6379 --fail-on high
./ORedisX --help
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
sudo strace -f -e trace=network ./ORedisX --help   # watch every network call
firejail --net=none ./ORedisX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
