# Enterprise SOC Home Lab — Architecture

**Project Status:** 🚧 Ongoing Development | Active Build & Testing

## Architecture Overview

This home lab uses VMware Workstation Pro to support an enterprise-style security monitoring environment. Wazuh SIEM centralizes security telemetry from Windows and Linux endpoints for detection, investigation, and monitoring.

## Infrastructure Components

| Component | Platform | Purpose |
|---|---|---|
| Wazuh Server | Ubuntu Server 24.04 LTS | Hosts Wazuh Manager, Indexer, and Dashboard |
| Windows11-Lab | Windows 11 | Endpoint monitoring, Windows logs, Sysmon, PowerShell, and Defender telemetry |
| Kali-Lab | Kali Linux | Linux endpoint monitoring and Suricata IDS |
| WIN11-ACER-LAB02 | Windows 11 | Additional registered endpoint; disconnected at the documented capture |
| Virtualization | VMware Workstation Pro | Virtualized lab infrastructure |

## Security Monitoring and Data Flow

1. Windows endpoints generate Windows Security, Sysmon, PowerShell, and Microsoft Defender events.
2. Wazuh agents collect configured endpoint telemetry and send it to the Wazuh Manager.
3. Suricata on Kali Linux generates network IDS events, which are collected and forwarded through the configured Wazuh integration.
4. Wazuh decodes and evaluates incoming events against built-in and custom detection rules.
5. Security alerts are indexed and made available for investigation through the Wazuh Dashboard.

## Network Architecture

The lab uses VMware NAT networking. Endpoint addresses, connectivity, and network details may change as the environment evolves.

## Detection Capabilities

- Windows Security Event Log monitoring
- Sysmon telemetry collection
- PowerShell-based detection testing
- Microsoft Defender monitoring
- File Integrity Monitoring (FIM)
- VirusTotal integration
- Suricata IDS alert ingestion
- Custom Wazuh detection rules
- MITRE ATT&CK-aligned detection validation

## Planned Enhancements

- Dedicated Windows target VM
- Active Directory test environment
- Expanded correlation and threat hunting workflows
- Wazuh Active Response and vulnerability management exercises

## Architecture Diagram

**Note:** This is an authorized home lab for defensive security research and professional portfolio development. It is not a production SOC deployment.
