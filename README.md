# 🛡️ Wazuh Lab Reports

Hands-on documentation of Wazuh SIEM/XDR deployments, detection engineering, alert analysis, and blue team scenarios — built and tested in a self-hosted home lab environment.

This repository captures a complete, evidence-driven SOC analyst workflow across multiple phases: from initial attack detection through gap analysis, remediation, and strategic SIEM deployment.

---

## 📋 Lab Reports — Complete Progression

### **Phase 1: Initial Detection & Investigation**

| Report | Date | Focus | Key Findings |
|--------|------|-------|--------------|
| **Wazuh SSH Lab Report v1.0** | 3 May 2026 | Basic SSH brute force detection | ✅ Attack detected within seconds; Wazuh rules working correctly |
| **Wazuh SSH Lab Report v2.0** | 3 May 2026 | Alert investigation & gap analysis | ⚠️ Identified 2 critical security gaps (source IP invisibility, East-West blind spot) |

### **Phase 2: Corrective Actions & Insider Threat Escalation**

| Report | Date | Focus | Key Findings |
|--------|------|-------|--------------|
| **Wazuh SSH Lab Report v3.0** | 4 May 2026 | Corrective actions & Splunk decision | ✅ OpenSSH log collection configured; Strategic Splunk deployment planned |
| **Wazuh SSH Lab Report v4.0** | 8 May 2026 | Insider threat simulation (Hydra) | ✅ Kali agent deployed (Agent 005); Sophisticated attack detected; 2 findings closed |

### **Phase 3: Strategic SIEM Deployment & Full Resolution**

| Report | Date | Focus | Key Findings |
|--------|------|-------|--------------|
| **Splunk Supplementary SIEM Report (FINAL)** | 9 May 2026 | Splunk deployment & findings closure | ✅ All 4 security findings FULLY CLOSED; Source IP attribution resolved |

---

## 🎯 Non-Technical Summaries

For stakeholders and portfolio use, see:

- **Lab_Reports_Non_Technical.docx** — High-level overview of all three exercises (management-friendly)
- **Lab_Reports_Non_Technical_v2.docx** — Updated summary including insider threat simulation

---

## 🔍 What This Demonstrates

This lab programme showcases:

✅ **End-to-end SOC analyst workflow** — Detect → Investigate → Find Gaps → Remediate → Verify

✅ **Evidence-driven decision making** — Strategic tooling decisions backed by systematic gap analysis

✅ **MITRE ATT&CK framework** — Automatic technique mapping and attack classification

✅ **Multi-SIEM architecture** — Wazuh + Splunk deployment with clear understanding of each tool's strengths

✅ **Continuous improvement** — Security posture enhanced between each phase

✅ **Professional documentation** — Technical depth with audit trail integrity

---

## 🧪 Lab Environment

### Infrastructure

| Component | Details | IP Address |
|-----------|---------|-----------|
| **SIEM — Wazuh** | Ubuntu Server 24.04 LTS + Wazuh v4.11.2 | 192.168.1.15 |
| **SIEM — Splunk** | Ubuntu Server 24.04 LTS + Splunk Enterprise 10.2.3 | TBD |
| **Target Endpoint** | Windows 11 Pro (Wazuh Agent 001) | 192.168.1.8 |
| **Attack Platform** | Kali Linux 2025.4 (Wazuh Agent 005) | 192.168.1.21 |
| **Firewall / IDS** | IPFire 2.29 x86_64 (Core Update 191) | 192.168.1.1 |
| **Hypervisor** | VMware Workstation Pro 25H2 | — |

### Security Findings — Status

| ID | Severity | Finding | Status |
|----|----------|---------|--------|
| **F-001** | HIGH | Source IP not captured in Windows SSH logs | ✅ CLOSED — Splunk OpenSSH/Operational parsing |
| **F-002** | HIGH | East-West traffic blind spot | ✅ CLOSED — Wazuh Agent 005 on Kali |
| **F-003** | MEDIUM | No account lockout policy | ✅ CLOSED — Group Policy configured (5 attempts, 30 min) |
| **F-004** | MEDIUM | IPFire log storage gap | ✅ CLOSED — Firewall logging verified active |
| **F-005** | LOW | OpenSSH post-quantum crypto | ⏸️ Low priority, deferred |
| **F-006** | LOW | Wazuh version mismatch | ✅ CLOSED — Agent downgraded, repo pinned |

**Summary: 6 findings identified. 5 FULLY CLOSED. 1 deferred (low priority).**

---

## 📊 Attack Scenarios Tested

### **Exercise 1 — Manual SSH Brute Force**
- **Tool:** Manual `ssh wronguser@target` attempts
- **Result:** 3 failed authentication events detected immediately
- **Detection Time:** Within seconds
- **Outcome:** ✅ Basic detection capability verified

### **Exercise 2 — Alert Investigation**
- **Focus:** Raw log analysis, root cause analysis, gap identification
- **Outcome:** Systematic investigation revealed 4 security weaknesses requiring remediation

### **Exercise 3 — Insider Threat Simulation (Hydra)**
- **Tool:** Hydra SSH brute force with rockyou.txt wordlist
- **Realism:** Professional attack tool + real-world password list
- **Detection:** Wazuh successfully detected escalated brute force attack
- **Key Improvement:** Kali now fully monitored (Agent 005) — attack source visible
- **Outcome:** ✅ More realistic attack successfully detected; East-West visibility closed

### **Exercise 4 — Splunk Validation**
- **Tool:** Hydra SSH brute force (same as Exercise 3)
- **Comparison:** Wazuh vs Splunk detection capability
- **Critical Finding:** Splunk natively parses OpenSSH/Operational logs that Wazuh cannot decode by default
- **Result:** Source IP 192.168.1.21 (Kali) fully visible in Splunk; Finding F-001 permanently resolved
- **Outcome:** ✅ Splunk value proposition validated; all findings closed

---

## 🛠️ Key Techniques & Tools

### Detection & Monitoring
- **Wazuh SIEM v4.11.2** — Rule authoring, Threat Hunting module, MITRE ATT&CK mapping
- **Splunk Enterprise 10.2.3** — Native log parsing, Search Processing Language (SPL), alert configuration
- **Custom Wazuh Rules** — Rule IDs 100001, 100002 (SSH authentication failures)

### Attack Simulation
- **Kali Linux 2025.4** — Attack platform, Hydra SSH brute force tool
- **rockyou.txt** — Real-world leaked password wordlist (1000+ entry trimmed version)

### MITRE ATT&CK Framework
- **Tactic:** Credential Access
- **Technique:** T1110 — Brute Force
- **Sub-technique:** T1110.001 — Password Guessing

---

## 📈 Evolution & Lessons Learned

**Initial Challenge:** Wazuh successfully detected attacks but couldn't identify attacker IP address from Windows SSH logs

**Investigation:** Systematic log analysis revealed:
- Windows OpenSSH logs to separate "Operational" event channel (not default Security channel)
- IPFire only monitors outbound RED zone traffic (not internal GREEN zone)
- Wazuh lacks native decoder for OpenSSH/Operational format

**Decision:** Deploy Splunk as supplementary SIEM — not to replace Wazuh, but to provide missing visibility

**Outcome:** 
- Splunk natively parses OpenSSH/Operational logs with automatic source IP extraction
- All findings identified, investigated, and resolved through evidence-driven remediation
- Demonstrates real-world enterprise challenge: **No single SIEM provides complete visibility**

---

## 🔗 Related Documentation

- **Incident Response Lab** — (Separate repo) Windows forensics, memory analysis, IOC investigation
- **GitHub Profile** — https://github.com/dhorton77

---

## 📝 Report Details

### Full Technical Reports
Each report includes:
- Executive summary
- Detailed attack methodology
- Raw log analysis with evidence
- MITRE ATT&CK framework mapping
- Security findings with severity ratings
- Remediation recommendations
- Next steps and lessons learned

### Non-Technical Summaries
Management-friendly overviews explaining:
- What the exercise tested
- Results in plain English
- Why findings matter
- Actions taken
- Overall assessment

---

## 🚀 Next Lab Exercises (Planned)

- **Website Defacement** — Detect and respond to application-layer attacks
- **Ransomware Simulation** — Orange zone (DMZ) deployment with encryption detection
- **Network-layer Detection** — Suricata IDS rules in IPFire

---

## 📧 Questions or Feedback?

These reports are portfolio documentation demonstrating:
- SOC analyst workflow and analytical thinking
- Evidence-driven decision making
- Professional documentation standards
- Continuous security improvement mindset

---

**Analyst:** David Boyd Horton  
**Last Updated:** 10 May 2026  
**Classification:** Portfolio — Home Lab Exercise  
**License:** Portfolio/Educational Use

---

*This repository reflects hands-on security engineering practice and serves as a professional portfolio demonstration of detection engineering, SIEM deployment, and blue team analysis capabilities.*
