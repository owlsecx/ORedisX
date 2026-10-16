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

Offline Redis / Valkey / KeyDB configuration security auditor

---

## ✨ Features

- Faithful redis.conf / valkey.conf / keydb.conf parser (sdssplitargs quoting, include chains, glob includes, last-wins semantics, per-directive file:line origin)
- ACL engine — inline `user` rules and external aclfile, nopass / plaintext / weak-secret / over-privilege
- Network exposure — bind, protected-mode, unix socket, unauthenticated reachability correlation
- Dangerous command matrix — FLUSHALL, FLUSHDB, CONFIG, DEBUG, KEYS, SLAVEOF/REPLICAOF, MODULE, EVAL ... with rename-command + ACL awareness
- TLS review — tls-port, protocols, ciphers, client auth, replication & cluster bus encryption
- Persistence abuse — dir / dbfilename write-primitive detection (ssh keys, cron, web roots, world-writable)
- File-permission audit of conf, ACL, includes, data
- Offline --root tree discovery + systemd unit checks
- Optional safe --probe (PING / INFO only, no auth)
- CWE + MITRE ATT&CK mapping, score & grade
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Self-test --demo, CI gates --fail-on / --min-severity

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ORedisX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
