# 🦉 ORedisX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OScan-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
