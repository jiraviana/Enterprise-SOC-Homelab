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

## Wazuh SIEM Architecture

The SOC lab uses Wazuh SIEM 4.14.8, deployed on Ubuntu Server 24.04 LTS, with the following core components:

| Component | Function |
|---|---|
| Wazuh Manager | Receives and analyzes endpoint security telemetry, processes events, and evaluates detection rules |
| Wazuh Indexer | Stores and indexes security alerts for searching and analysis |
| Wazuh Dashboard | Provides centralized security monitoring, alert investigation, and visualization |
| Wazuh Agents | Collect configured Windows and Linux endpoint security telemetry |

### Security Event Processing

1. Endpoint activity generates security telemetry.
2. Wazuh agents forward configured events to the Wazuh Manager.
3. The Manager processes events using decoders and detection rules.
4. Generated alerts are forwarded to the Wazuh Indexer.
5. Security analysts review alerts through the Wazuh Dashboard.

## Security Monitoring and Data Flow

1. Windows endpoints generate Windows Security, Sysmon, PowerShell, and Microsoft Defender events.
2. Wazuh agents collect configured endpoint telemetry and send it to the Wazuh Manager.
3. Suricata on Kali Linux generates network IDS events, which are collected and forwarded through the configured Wazuh integration.
4. Wazuh decodes and evaluates incoming events against built-in and custom detection rules.
5. Security alerts are indexed and made available for investigation through the Wazuh Dashboard.

## Network Architecture

The lab uses VMware NAT networking. Endpoint addresses, connectivity, and network details may change as the environment evolves.

VMware NAT networking provides connectivity for the virtual machines through the host's virtual networking infrastructure.

Suricata is deployed on Kali Linux to inspect traffic available to its configured network interface. Its visibility depends on the traffic routing and capture configuration; it does not automatically monitor all traffic across the VMware NAT network.

## Security Monitoring and Detection Capabilities

- Windows Security Event Log monitoring
- Sysmon telemetry collection
- PowerShell-based detection testing
- Microsoft Defender monitoring
- File Integrity Monitoring (FIM)
- VirusTotal integration
- Suricata IDS alert ingestion
- Custom Wazuh detection rules
- MITRE ATT&CK-aligned detection validation

For technical infrastructure details, see the [Back to Main Project README](../README.md)

### External Threat Intelligence

VirusTotal is integrated with Wazuh to support file hash reputation checks during relevant security investigations.

VirusTotal is an external threat intelligence service and is not hosted within the VMware lab environment.

## Planned Enhancements

- Dedicated Windows target VM
- Active Directory test environment
- Expanded correlation and threat hunting workflows
- Wazuh Active Response and vulnerability management exercises

## Architecture Diagram

The following diagram illustrates the deployed Wazuh SOC lab infrastructure, monitored endpoints, security telemetry flow, and planned enhancements.

![Enterprise SOC Home Lab Architecture](Enterprise-SOC-Lab-Architecture.jpeg)

**Note:** This is an authorized home lab for defensive security research and professional portfolio development. It is not a production SOC deployment.
