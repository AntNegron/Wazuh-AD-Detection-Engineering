# Wazuh-AD-Detection-Engineering
A detection engineering lab focused on integrating Windows Defender logs into Wazuh and validating detections against MITRE ATT&amp;CK techniques.

Detection Engineering Lab: Wazuh SIEM & Active Directory Integration
Executive Summary
This project involved deploying a centralized Wazuh SIEM within a multi-VM Active Directory environment to monitor enterprise security telemetry. The core objective was to enhance visibility by integrating Windows Defender Operational logs and validating the defensive posture against specific MITRE ATT&CK techniques using Atomic Red Team.

Technical Environment:
SIEM: Wazuh Manager (Ubuntu)
Endpoints: Windows Server (Domain Controller) and Windows 10 Workstations.
Logging Tools: Sysmon, Windows Event Forwarding, and Windows Defender.
Attack Simulation: Atomic Red Team and custom PowerShell scripts.

Key Modifications & Configurations
Windows Defender Log Integration: I successfully expanded the Wazuh monitoring scope by adding the Windows Defender event channel as a new log source. This provided critical visibility into malware detections, remediation actions, and real-time endpoint protection events.

Security Experiments & Validated Detections
I executed three primary experiments to test the detection capabilities of the environment:
MITRE ID,Technique,Simulation Tool,Detection Outcome
T1566.001,Phishing: Spearphishing Attachment,Atomic Red Team,Confirmed logging of malicious attachment execution.  
T1047,Windows Management Instrumentation (WMI),Sysmon / MITRE,Detected unauthorized WMI execution for persistence.  
T1059.003,PowerShell Abuse,Custom Scripts / Defender,Validated Defender's reaction to malicious PowerShell commands.  

[Copy of [Sprint 11] Plan Proposal {Anthony Negron}.pdf](https://github.com/user-attachments/files/27486184/Copy.of.Sprint.11.Plan.Proposal.Anthony.Negron.pdf)
