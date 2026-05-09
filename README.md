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
| IPFire 2.29 | Perimeter firewall / log source
