# Enterprise SOC Home Lab | Wazuh SIEM

**Project Status: 🚧 Ongoing Development | Active Build & Testing**

> This is an ongoing cybersecurity engineering project. Features, integrations, detection rules, attack simulations, and documentation are continuously being developed, tested, and improved. Completed implementations are documented with validation evidence, while upcoming capabilities are tracked in the project roadmap.

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
