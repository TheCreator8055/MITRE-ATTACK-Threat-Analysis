# MITRE ATT&CK Threat Analysis & Incident Mapping Lab

![Framework](https://img.shields.io/badge/Framework-MITRE_ATT%26CK-red)
![Platform](https://img.shields.io/badge/Platform-Kali_Linux_%7C_Wazuh_SIEM-blue)
![Focus](https://img.shields.io/badge/Focus-SOC_Operations_%26_Threat_Hunting-brightgreen)

## Overview

This repository documents hands-on threat intelligence mapping, adversary emulation, and Blue Team detection engineering aligned with the **MITRE ATT&CK Enterprise Framework**. 

Each case study translates multi-stage cyberattacks across Windows, Linux, and Cloud environments into structured Tactics, Techniques, and Sub-Techniques—paired with endpoint/network telemetry indicators, SIEM/XDR detection logic, and actionable mitigations.

---

## Repository Index & Case Studies

| ID | Incident / Lab Scenario | Target Environment | Key Tactics Covered | Key Techniques Mapped | Defensive Focus |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **01** | [The Friday Night Breach](./01-Windows-Ransomware-Breach/Incident-Report.md) | Windows Enterprise & Active Directory | Reconnaissance, Initial Access, Credential Access, Lateral Movement, Impact | `T1597.002`, `T1078`, `T1003.001`, `T1021.001`, `T1486` | LSASS Memory Protection (Sysmon ID 10), RDP Lateral Movement Auditing |
| **02** | [The Silent Data Leak](./02-Corporate-Espionage-Leak/Incident-Report.md) | Windows Endpoint & Cloud Storage | Initial Access, Execution, Defense Evasion, Discovery, C2, Exfiltration | `T1566.001`, `T1204.002`, `T1059.001`, `T1070.001`, `T1071.001`, `T1537` | Event Log Clearing Alerts (Event ID 1102), Cloud DLP & Egress Monitoring |
| **03** | [The Midnight Web Server Takeover](./03-Linux-WebServer-Takeover/Incident-Report.md) | Linux Web Server & SSH Infrastructure | Reconnaissance, Initial Access, Persistence, Privilege Escalation, Credential Access, Impact | `T1595.002`, `T1190`, `T1059.004`, `T1053.003`, `T1548.001`, `T1552.004`, `T1565.001` | Crontab Integrity Monitoring, SUID Abuse (`auditd`), SSH Key FIM |

---

## Lab Environment & Tooling

* **Offensive Testing & Emulation:** Kali Linux (Live USB 3.2 Persistence), Nmap, Hydra, Burp Suite, Wireshark, tcpdump
* **Threat Intelligence & Visualization:** MITRE ATT&CK Enterprise Matrix, MITRE ATT&CK Navigator (`.json` layer exports)
* **Log Sources Analyzed:** Windows Security Event Logs (`4624`, `4625`, `1102`), Sysmon (`Event ID 1`, `10`), Linux `auditd` & `auth.log`, DNS & HTTP Proxy Logs

---

## Methodology

Every incident report in this repository follows a standardized **Purple Team** workflow:

1. **Kill Chain Reconstruction:** Break down raw attack narratives and command-line artifacts into chronological ATT&CK Tactics.
2. **Granular Technique Mapping:** Identify exact Technique and Sub-Technique IDs (e.g., differentiating `T1110.003 Password Spraying` from standard brute force).
3. **Navigator Layer Export:** Generate visual heatmaps using **MITRE ATT&CK Navigator** to highlight attacker coverage across the matrix.
4. **Detection & Mitigation Engineering:** Document specific log event IDs, file paths, or network signatures required to alert on and block each stage.

---

##  Folder Structure

```text
MITRE-ATTACK-Threat-Analysis/
├── README.md
├── 01-Windows-Ransomware-Breach/
│   ├── Incident-Report.md
│   └── attack-navigator-layer.json
├── 02-Corporate-Espionage-Leak/
│   ├── Incident-Report.md
│   └── attack-navigator-layer.json
├── 03-Linux-WebServer-Takeover/
    ├── Incident-Report.md
    └── attack-navigator-layer.json

```

---
