# Enterprise SOC Home Lab | Wazuh SIEM

**Project Status: 🚧 Ongoing Development | Active Build & Testing**

> This is an ongoing cybersecurity engineering project. Features, integrations, detection rules, attack simulations, and documentation are continuously being developed, tested, and improved. Completed implementations are documented with validation evidence, while upcoming capabilities are tracked in the project roadmap.

## Project Navigation

| Section | Description |
|---|---|
| [Project Objectives](#project-objectives) | Purpose and goals of the SOC lab |
| [Lab Environment](#lab-environment) | Infrastructure and technologies used |
| [Wazuh SIEM Dashboard](#wazuh-siem-dashboard) | SIEM deployment evidence |
| [Multi-Endpoint Monitoring](#multi-endpoint-monitoring) | Windows and Linux endpoint monitoring |
| [Custom Detection Engineering](#custom-detection-engineering) | Validated detection rules and evidence |
| [MITRE ATT&CK Simulations](attack-simulations/README.md) | Controlled testing and simulation tracking |
| [Detection Case Study — T1562.001](detection-rules/T1562.001-Defender-Impairment.md) | Microsoft Defender command-pattern detection |
| [Project Roadmap](#project-roadmap) | Completed, ongoing, and planned work |
| [Screenshots and Evidence](screenshots/README.md) | Supporting lab screenshots |
| [Lab Architecture](architecture/README.md) | Infrastructure documentation |

### Security Monitoring • Detection Engineering • Threat Hunting • Incident Response

A hands-on, enterprise-style Security Operations Center (SOC) home lab designed to simulate real-world security monitoring, threat detection, incident investigation, and response workflows.

This project demonstrates practical cybersecurity engineering skills through the deployment and configuration of Wazuh SIEM, endpoint monitoring, custom detection rules, security telemetry collection, and MITRE ATT&CK-aligned attack simulations.

## Project Objectives

- Build and maintain a functional, multi-endpoint SOC environment.
- Centralize Windows and Linux security logs using Wazuh.
- Develop and test custom detection rules.
- Simulate adversary techniques mapped to MITRE ATT&CK.
- Investigate alerts and document security incidents.
- Implement additional security monitoring and response capabilities.

## Lab Environment

| Component | Technology |
|---|---|
| SIEM Platform | Wazuh 4.14.8 |
| SIEM Server | Ubuntu Server 24.04 LTS |
| Virtualization | VMware Workstation Pro |
| Windows Endpoint | Windows 11 |
| Linux Endpoint | Kali Linux |
| Endpoint Protection | Microsoft Defender |
| Threat Intelligence | VirusTotal |
| Attack Framework | MITRE ATT&CK |

## Wazuh SIEM Dashboard

The screenshot below shows my deployed Wazuh SIEM
environment during active lab testing.

![Wazuh SOC Lab Dashboard](screenshots/01-wazuh-dashboard.png)

**Dashboard observations:**
- Centralized security monitoring through Wazuh
- Active endpoint agents reporting to the SIEM
- Security alerts across multiple severity levels
- Ongoing endpoint monitoring and detection testing

**Project Status:** Ongoing development and testing.

> Note: Agent connectivity and alert counts reflect
> the environment at the time of capture.

## Multi-Endpoint Monitoring

This ongoing SOC lab includes Wazuh agents deployed
across Windows and Linux endpoints, enabling
centralized security monitoring.

![Wazuh Agent Monitoring](screenshots/02-wazuh-connected-agents.png)

### Registered Endpoints

| Endpoint | Operating System | Status at Capture |
|---|---|---|
| Windows11-Lab | Windows 11 | Active |
| Kali-Lab | Kali Linux | Active |
| WIN11-ACER-LAB02 | Windows 11 | Disconnected |

### Monitoring Capabilities

- Centralized Windows and Linux security telemetry
- Wazuh agent deployment and management
- Endpoint connection and health monitoring
- Security alert collection and investigation

**Project Status:** Ongoing development and testing.

> Agent statuses reflect the environment at
> the time of capture.

## Implemented Capabilities

- Wazuh Manager, Indexer, and Dashboard deployment
- Windows and Linux agent integration
- Windows Security Event Log monitoring
- File Integrity Monitoring (FIM)
- VirusTotal integration
- Microsoft Defender security telemetry
- EICAR antivirus detection testing
- Custom Wazuh detection rules
- MITRE ATT&CK-aligned detection testing

## Detection Engineering

Custom Wazuh rules are being developed and tested to identify suspicious endpoint activities.

### Example: MITRE ATT&CK T1562.001

**Technique:** Impair Defenses — Disable or Modify Tools

**Detection objective:** Identify PowerShell commands associated with attempts to disable Microsoft Defender real-time protection.

**Detection evidence:**
- Endpoint: Windows11-Lab
- Custom Rule ID: 100109
- Alert Severity: Level 12
- Detection Source: PowerShell command telemetry

The custom detection was validated using a controlled test string in the lab environment.

## Project Roadmap

Planned improvements include:

- Sysmon deployment and integration
- Enhanced PowerShell logging
- Advanced event correlation
- Suricata network intrusion detection
- Additional MITRE ATT&CK simulations
- Threat hunting case studies
- Wazuh Active Response
- Vulnerability detection and management
- Dedicated Windows target virtual machine
- Active Directory lab environment

## Project Documentation

This repository will contain architecture diagrams, configuration examples, detection rules, screenshots, attack simulation procedures, investigation reports, and lessons learned as the project develops.

## Disclaimer

This project is developed for educational, defensive security research, and professional portfolio purposes. All testing is performed in an authorized home lab environment. Sensitive credentials, private keys, and confidential information are excluded from this repository.

## Custom Detection Engineering

As part of my ongoing Wazuh SOC Home Lab, I develop, test, and validate custom detection rules to identify suspicious endpoint activity and map relevant behaviors to the MITRE ATT&CK framework.

### Detection Case Study 01 — Microsoft Defender Tampering

| Field | Details |
|---|---|
| MITRE ATT&CK | T1562.001 — Impair Defenses: Disable or Modify Tools |
| Wazuh Rule ID | 100109 |
| Alert Severity | Level 12 |
| Windows Event ID | 4104 — PowerShell Script Block Logging |
| Endpoint | Windows11-Lab |
| Validation Method | Controlled PowerShell command-pattern test |
| Detection Status | Validated — Further testing ongoing |

### Detection Evidence

![Microsoft Defender Tampering Detection](screenshots/MITRE-T1562.001-Defender-Tampering-Detection.png.jpeg)

### Investigation Summary

A custom Wazuh detection rule identified a PowerShell script-block pattern associated with attempts to disable Microsoft Defender real-time protection.

The controlled test successfully generated a Level 12 security alert mapped to MITRE ATT&CK T1562.001. The validation confirms that the detection identified the suspicious command pattern; it does not establish that Microsoft Defender was actually disabled.

### Detailed Detection Engineering Documentation

**[View Full MITRE T1562.001 Detection Case Study](detection-rules/T1562.001-Defender-Impairment.md)**

### Ongoing Detection Engineering

Additional custom detection rules, MITRE ATT&CK simulations, correlation logic, and investigation evidence will be documented as development and testing progress.

> **Project Status:** Ongoing Development | Active Build & Testing
