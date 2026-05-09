# Centralized SIEM System Using Splunk Enterprise for Real-Time Multi-Platform Log Aggregation and Threat Detection

![Splunk](https://img.shields.io/badge/Splunk-Enterprise_9.x-65A637?style=flat-square&logo=splunk&logoColor=white)
![Windows](https://img.shields.io/badge/Indexer-Windows-0078D6?style=flat-square&logo=windows&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Forwarder-Kali_Linux-268BEE?style=flat-square&logo=kalilinux&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)

A final year capstone project implementing a fully functional SIEM pipeline — Splunk Enterprise on Windows as the central indexer, with a Universal Forwarder on Kali Linux shipping logs in real time over TCP 9997.

---

## Architecture

```
Kali Linux (Forwarder)          TCP :9997          Windows Host (Indexer)
├── /var/log/syslog        ─────────────────►      ├── Splunk Enterprise
├── /var/log/auth.log                              ├── Web UI :8000
├── File Integrity Monitor                         ├── Windows Event Logs
└── kern.log                                       └── Performance Counters
```

## What's Monitored

| Source | Type |
|--------|------|
| Windows Event Logs | Application, Security, System |
| Performance Counters | CPU, Memory, Disk, Network |
| Linux Syslog | `/var/log/syslog`, `auth.log`, `kern.log` |
| File Integrity | `/etc/passwd`, `/etc/shadow`, `/etc/sudoers` |

## Key Ports

| Port | Purpose |
|------|---------|
| `9997` | Forwarder → Indexer data ingestion |
| `8000` | Splunk Web UI |

## Stack

`Splunk Enterprise x.x` · `Splunk Universal Forwarder` · `SPL` · `PowerShell` · `Bash`

---

## Documentation

Full step-by-step implementation guide is included in [`docs/`](docs/) — covering installation, configuration, dashboard creation, and verification steps.
