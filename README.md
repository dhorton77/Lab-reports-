# 🛡️ Wazuh Lab Reports

Hands-on documentation of Wazuh SIEM/XDR deployments, detection engineering, alert analysis, and blue team scenarios — built and tested in a self-hosted home lab environment.

---

## 🧪 Lab Environment

This lab is hosted on **VMware Workstation** and spans multiple categories of virtual machines designed to simulate real-world enterprise environments, adversary targets, and security tooling.

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
| Windows 11 x64 | Modern endpoint |
| Windows 11 Workstation x64 | Workstation-class endpoint |

### 🔥 Firewalls & Network
| VM | Purpose |
|---|---|
| IPFire | Perimeter firewall / log source |
| PFsense | Network firewall / traffic analysis |

### 🔬 Forensics & Offensive Tooling
| VM | Purpose |
|---|---|
| Kali Linux Purple | Purple team operations |
| Kali Linux 2025.4 | Offensive security / red team |
| SIFT Workstation | Digital forensics & incident response |

### 📡 SIEM & Analytics
| VM | Purpose |
|---|---|
| Ubuntu 64-bit (Wazuh) | Wazuh manager / indexer / dashboard |
| Ubuntu 64-bit (SIEM) | Supporting SIEM infrastructure |
| SOF-ELK | ELK-based log analysis |
| VMware ESXi 7 | Nested ESXi — Network+ lab testing only |

---

## 📁 Report Index

| # | Report Title | Category | Date |
|---|---|---|---|
| 001 | [Wazuh SSH Lab Report](Wazuh_SSH_Lab_Report_v4.docx) | Detection / Authentication | May 2026 |
| 002 | [Non-Technical Lab Report](Lab_Reports_Non_Technical_v2.docx) | Documentation | May 2026 |

> Reports will be added as labs are completed. Each report includes objectives, methodology, findings, and screenshots.

---

## 🎯 Objectives

- Deploy and configure Wazuh in a realistic multi-OS environment
- Develop and tune custom detection rules
- Simulate adversary techniques against vulnerable targets
- Document findings in a structured, repeatable format
- Build a portfolio of blue team detection scenarios

---

## 🛠️ Core Tools & Versions

| Tool | Version / Notes |
|---|---|
| Wazuh | Latest stable (Ubuntu-hosted) |
| VMware Workstation | Host hypervisor |
| Kali Linux | 2025.4 |
| SIFT Workstation | Latest |
| SOF-ELK | Latest |

---

## 📌 Notes

- All activity is conducted in an isolated, self-hosted lab environment
- No live/production systems are involved
- Labs are for educational and professional development purposes

---

*Maintained by Davey — Desktop Consultant | CompTIA Security+ | Network+ | Server+ | A+*
