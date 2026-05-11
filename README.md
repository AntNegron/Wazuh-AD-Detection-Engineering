# SIEM Engineering: Wazuh & Active Directory Detection Lab
![Lab-Status](https://img.shields.io/badge/Status-Completed-success) ![Wazuh](https://img.shields.io/badge/Tools-Wazuh--SIEM-orange) ![MITRE](https://img.shields.io/badge/Framework-MITRE--ATT%26CK-red)

## 📌 Executive Summary
This project involved deploying a centralized **Wazuh SIEM** within a multi-VM **Active Directory** environment to monitor enterprise security telemetry. The objective was to build a visibility-first defense posture by integrating Windows Defender, Sysmon, and AD logs to detect and analyze adversary behavior in real-time.

👉 **[Read the Full Technical Breakdown & Screenshots Here](https://0x2asecurity.com/siem-engineering/2025/building-my-first-siem-lab-detecting-real-attacks-my-cybersecurity-journey-begins/)**

---

## 🛠 Technical Environment
* **SIEM/XDR:** Wazuh Manager (Ubuntu)
* **Endpoints:** Windows Server 2022 (Domain Controller) & Windows 10 Workstations
* **Logging Tools:** Sysmon, Windows Defender, Windows Event Forwarding
* **Attack Simulation:** Kali Linux (Hydra, Mimikatz), Atomic Red Team, PowerShell

---

## 🚀 Key Configurations
* **Windows Defender Integration:** Expanded the Wazuh monitoring scope by adding the Windows Defender event channel as a log source. This provides real-time visibility into malware remediations and endpoint protection events.
* **Sysmon Enhancement:** Deployed a custom Sysmon configuration to track process creation, network connections, and credential access that standard logs miss.
* **Alert Customization:** Configured Wazuh rules to trigger alerts specifically for lateral movement and credential dumping.

---

## 🧠 Validated Detections (MITRE ATT&CK)
I executed specific experiments to validate that my SIEM was correctly parsing and alerting on malicious activity:

| MITRE ID | Technique | Simulation Tool | Detection Outcome |
| :--- | :--- | :--- | :--- |
| **T1110** | Brute Force | Hydra / Kali | **Success:** Identified rapid login failures and source IP. |
| **T1003** | OS Credential Dumping | Mimikatz | **Success:** Captured LSASS access and unauthorized tool execution. |
| **T1059.001** | PowerShell Abuse | Atomic Red Team | **Success:** Validated Defender alerts for encoded PS commands. |

---

## 📈 Final Results
By the end of this project, I achieved:
1. **Full Telemetry:** Unified logs from AD, Defender, and Sysmon into a single pane of glass.
2. **Reduced Blind Spots:** Validated that "silent" attacks like credential dumping now trigger high-severity alerts.
3. **Hardened Posture:** Implemented account lockout policies based on the findings from the brute-force simulations.
