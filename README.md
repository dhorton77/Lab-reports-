# 🛡️ Wazuh Lab Reports

Hands-on documentation of Wazuh SIEM/XDR deployments, detection engineering, alert analysis, and blue team scenarios — built and tested in a self-hosted home lab environment.

---

## 🧪 Lab Environment

This lab is hosted on **VMware Workstation Pro 25H2** and spans multiple categories of virtual machines designed to simulate real-world enterprise environments, adversary targets, and security tooling.

### 🔴 Vulnerable / Target Systems
| VM | Purpose |
|---|---|
| Mr Robot VM | CTF-style Linux target |
| VPLE | Vulnerable Linux practice environment |
| OWASP Broken Web Apps VM v1.2 | Web application vulnerability testing |
| Metasploitable2-Linux | Classic multi-vulnerability Linux target |

### 🪟 Legacy Operating Systems
| VM | Notes |
|---|---|
| Windows 10 x64 | Legacy endpoint simulation |
| Windows 7 | End-of-life OS detection testing |
| Windows Vista x64 Edition | Legacy endpoint |
| Windows XP Professional | End-of-life OS |
| Windows 98 | Historical / legacy |

### 🖥️ Servers
| VM | Purpose |
|---|---|
| Windows Server 2019 | Active Directory / endpoint agent testing |
| Windows Server 2016 Essentials | Server-based detection scenarios |

### 💻 Standalone Workstations
| VM | Notes |
|---|---|
| Windows 11 x64 | Modern endpoint — primary attack target |
| Windows 11 Workstation x64 | Workstation-class endpoint |

### 🔥 Firewalls & Network
| VM | Purpose |
|---|---|
| IPFire 2.29 | Perimeter firewall / log source — GREEN & RED zone logging active |
| PFsense | Network firewall / traffic analysis |

### 🔬 Forensics & Offensive Tooling
| VM | Purpose |
|---|---|
| Kali Linux Purple | Purple team operations |
| Kali Linux 2025.4 | Offensive security / red team — Wazuh Agent 005 deployed |
| SIFT Workstation | Digital forensics & incident response |

### 📡 SIEM & Analytics
| VM | Purpose |
|---|---|
| Ubuntu 64-bit (Wazuh) | Wazuh v4.11.2 manager / indexer / dashboard — 192.168.1.15 |
| Ubuntu 64-bit (SIEM) | Splunk Enterprise 10.2.3 — supplementary SIEM |
| SOF-ELK | ELK-based log analysis |
| VMware ESXi 7 | Nested ESXi — Network+ lab testing only |

---

## 📁 Report Index

| # | Report Title | Category | Date |
|---|---|---|---|
| 001 | [Wazuh SSH Lab Report v4.0](Wazuh_SSH_Lab_Report_v4.docx) | Detection / Authentication / Gap Analysis | 8 May 2026 |
| 002 | [Non-Technical Lab Report](Lab_Reports_Non_Technical_v2.docx) | Documentation | May 2026 |
| 003 | [Splunk Supplementary SIEM Report](Splunk_Supplementary_SIEM_Report_FINAL.docx) | Detection / SIEM Comparison / Remediation | 9 May 2026 |

> Reports will be added as labs are completed. Each report includes objectives, methodology, findings, and screenshots.

---

## 🔬 Latest Lab — SSH Brute Force Detection (May 2026)

A four-phase exercise covering attack simulation, alert investigation, gap analysis, SIEM deployment, and full remediation.

**Attack:** Hydra SSH brute force from Kali Linux (192.168.1.21) → Windows 11 (192.168.1.8)  
**MITRE ATT&CK:** T1110.001 — Brute Force: Password Guessing

### 🔍 Security Findings & Outcomes

| ID | Severity | Finding | Status |
|---|---|---|---|
| F-001 | 🔴 HIGH | Source IP not captured in Wazuh — Windows OpenSSH logs to a separate Operational channel | ✅ CLOSED — Resolved via Splunk ingesting OpenSSH/Operational log |
| F-002 | 🔴 HIGH | East-West traffic blind spot — Kali attack platform not monitored | ✅ CLOSED — Wazuh Agent 005 deployed on Kali Linux |
| F-003 | 🟡 MEDIUM | No account lockout policy on Windows 11 — unlimited guessing possible | ✅ CLOSED — Group Policy configured: 5 attempts, 30 min lockout. Windows confirmed account locked out. |
| F-004 | 🟡 MEDIUM | IPFire log storage gap — logs not appearing for 3 May 2026 | ✅ CLOSED — IPFire logging confirmed active: 15,835 hits on 8 May 2026 |

**All four findings closed. Clean sheet. ✅**

---

## 🎯 Objectives

- Deploy and configure Wazuh in a realistic multi-OS environment
- Simulate adversary techniques against vulnerable targets using professional tools (Hydra)
- Identify and document security gaps through systematic investigation
- Deploy supplementary SIEM (Splunk) to address identified limitations
- Remediate all findings and verify resolution with evidence
- Build a portfolio of blue team detection scenarios demonstrating end-to-end SOC analyst workflow

---

## 🛠️ Core Tools & Versions

| Tool | Version / Notes |
|---|---|
| Wazuh | v4.11.2 (Ubuntu-hosted) |
| Splunk Enterprise | 10.2.3 (Ubuntu-hosted) |
| VMware Workstation | Pro 25H2 — host hypervisor |
| Kali Linux | 2025.4 |
| Hydra | v9.6 — SSH brute force tool |
| IPFire | 2.29 x86_64 Core Update 191 |
| SIFT Workstation | Latest |
| SOF-ELK | Latest |

---

## 📌 Notes

- All activity is conducted in an isolated, self-hosted lab environment
- No live or production systems are involved
- Labs are for educational and professional development purposes only

---

*Maintained by Davey — Desktop Consultant | CompTIA Security+ | Network+ | Server+ | A+*
