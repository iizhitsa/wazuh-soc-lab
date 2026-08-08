# wazuh-soc-lab
SOC Home Lab (Wazuh SIEM/XDR, pfSense, Suricata, Sysmon) built for real-world threat detection, log monitoring, and attack simulation.

# 📌Overview
A hands-on project covering the end-to-end deployment and configuration of an open-source security stack, featuring Wazuh SIEM/XDR, Suricata IDS, and a pfSense firewall.

# 🏗️Lab Architecture
Environment hosted on VMware virtual machines, consisting of the following core segments:
* Wazuh Server: Acts as the central hub hosting the Manager, Indexer, and Dashboard to aggregate and analyze events from all endpoints, Suricata, and pfSense.
* Windows Endpoint (Windows 11 Pro): Monitored via the Wazuh Agent to track system activity and forward local security logs.
* Attacker Node (Kali Linux): A dedicated instance deployed to simulate cyber threats and malicious activities.
* pfSense Firewall: Secures network boundaries and forwards firewall logs to Wazuh for anomaly detection.
* Suricata IDS/IPS: Inspects live network traffic and feeds real-time intrusion alerts into the Wazuh SIEM.
<img width="1223" height="864" alt="Lab_architecture.png" src="https://github.com/iizhitsa/wazuh-soc-lab/blob/main/Lab_architecture.png" />

_Figure 1: SOC Lab Architecture._

# 🛠️ Wazuh Setup
[Wazuh_configuration.pdf](https://github.com/iizhitsa/wazuh-soc-lab/blob/main/docs/Wazuh_configuration-PO.pdf)

🎯 **Key Milestones**:
* Deploy Wazuh: Spin up the SIEM platform in a virtualized environment via the official OVA package.
* Configure & Verify: Set up core services, troubleshoot potential issues, and access the web dashboard.
* Centralize Visibility: Install and register endpoint agents to enable continuous log collection.

# 🔌 Implementaion & Configuration:
[Suricata_integration.pdf](https://github.com/iizhitsa/wazuh-soc-lab/blob/main/docs/Wazuh_configuration-PO.pdf)

🎯 **Key Milestones**:
* Threat Strategy Definition: Implement IDS for passive threat detection and IPS for active attack mitigation.
* Suricata Deployment: Install and configure the Suricata engine on Windows utilizing Npcap and custom detection rules.
* SIEM Integration: Unify security telemetry by shipping Suricata network logs to Wazuh for centralized monitoring.

[Pfsense_integration.pdf](https://github.com/iizhitsa/wazuh-soc-lab/blob/main/docs/Pfsense_integration-OP.pdf)

🎯 **Key Milestones**:
* Perimeter Defense Deployment: Set up pfSense as a virtual firewall within VMware to manage and monitor network traffic.
* Log Forwarding Integration: Configure remote syslog capabilities to stream pfSense security events into Wazuh.
* Custom Detection Tuning: Develop tailored Wazuh decoders and rules to identify allowed connections, blocked traffic, and authentication attempts.

[VirusTotal_integration.pdf](https://github.com/iizhitsa/wazuh-soc-lab/blob/main/docs/VirusTotal_integration-OP.pdf)

🎯 **Key Milestones**:
* API Integration Setup: Secure a VirusTotal API key and configure the integration module within the Wazuh Manager.
* Real-Time Directory Monitoring: Enable Wazuh FIM (File Integrity Monitoring) agents to track directories and automate VirusTotal lookups.
* Alert Enrichment: Leverage VirusTotal reputation data to enrich SIEM alerts, accelerating incident triage and threat analysis.

[File_integrity_monitoring-OP.pdf](https://github.com/user-attachments/files/30853842/File_integrity_monitoring-OP.pdf)



🎯 **Key Milestones**:
* FIM Policy Definition: Configure Wazuh File Integrity Monitoring (FIM) on Windows by auditing specific directories in the agent’s ossec.conf.
* Real-Time Auditing: Enable continuous, recursive monitoring with change-reporting capabilities for targets and subfolders.
* Alert Validation: Create, modify, and delete files to verify that the SIEM successfully triggers alerts for every file system event.

[Logs&Sysmon_ingestion.pdf](https://github.com/iizhitsa/wazuh-soc-lab/blob/main/docs/Logs%26Sysmon_ingestion-OP.pdf)


🎯 **Key Milestones**:
* Telemetry Baseline Assessment: Analyze Windows Event Logs to identify key categories and critical Event IDs essential for system and security visibility.
* Advanced Endpoint Logging: Deploy Sysmon to capture granular system events and enhance the detection of anomalous or adversarial behavior.
* Log Aggregation & Correlation: Ingest Sysmon logs into Wazuh to enable centralized monitoring, event correlation, and custom rule-based alerting.

# 🔐 Brute Force Attack: Simulation, Detection & Defense:

Brute Force Attack Simulation & Wazuh Investigation 

[SSH_Brute_Force.pdf](https://github.com/iizhitsa/wazuh-soc-lab/blob/main/docs/SSH_Brute_Force-OP.pdf)

🎯 **Key Milestones**:
* Adversary Emulation: Simulate an SSH brute force attack using Hydra within a controlled environment to generate high-frequency failed login attempts.
* Detection & Correlation: Identify malicious behavior in Wazuh using Windows Event Logs (e.g., Event ID 4625) and correlation rules tuned for authentication failures.
* Defensive Remediation: Implement strong password policies, account lockouts, and configure Wazuh Active Response to automatically block brute-force threats.

**⚠️ Important**: Perform these simulation activities strictly inside an isolated lab environment or on authorized systems. Never execute brute-force testing against third-party or production infrastructure.

# 🏁 Conclusion & Key Takeaways
This SOC home lab project successfully demonstrates the power of combining open-source tools to engineer a fully functional security monitoring and detection environment. By establishing Wazuh as the central SIEM hub and integrating it with pfSense, Suricata, and Sysmon, the architecture accurately replicates the core telemetry stack of a modern Security Operations Center.Key Achievements:Enhanced Telemetry: Integrated VirusTotal API and File Integrity Monitoring (FIM) to elevate alert context and speed up threat analysis.Validated Detection: Proven capability to ingest, correlate, and surface high-fidelity alerts through real-world threat emulation (Hydra brute-force testing).Analyst Workflow Alignment: Replicated the end-to-end incident response cycle—from initial detection and triage to automated remediation.This project has significantly reinforced critical blueprint skills for a SOC Analyst, including deep-dive log analysis, correlation rule engineering, alert triage, and proactive threat hunting.

**🎓 Educational Notice**: This repository is developed purely for educational and defensive research purposes. Unauthorized use of these methodologies outside a controlled lab environment is strictly prohibited.

# 📄 Full Documentation

Get the complete SOC Home Lab setup guide here:

[Soc_Home_Lab.pdf](https://github.com/iizhitsa/wazuh-soc-lab/blob/main/docs/Soc_Home_Lab-OP.pdf)


# 📌 Connect with Me:
[Telegram](t.me/f0rbrt)
