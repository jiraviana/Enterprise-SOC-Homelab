# Wazuh Custom Detection Rules

This folder contains custom detection engineering work developed and tested in my Wazuh Home SOC Lab.

## Objectives

- Develop custom Wazuh detection rules.
- Detect suspicious Windows and Linux activities.
- Map detections to MITRE ATT&CK techniques.
- Validate detections using controlled simulations.
- Document alert evidence and investigation results.

## Implemented Detection Example

### MITRE ATT&CK T1562.001

Technique: Impair Defenses - Disable or Modify Tools

Rule ID: 100109

Severity: Level 12

Detection: PowerShell command pattern associated with disabling Microsoft Defender real-time protection.

Status: Tested in lab environment.


## Custom Detection Inventory

The following custom Wazuh detection rules have generated alerts in my SOC home lab. Additional validation and investigation documentation is ongoing.

| Rule ID | MITRE ATT&CK | Detection Use Case | Status |
|---|---|---|---|
| 100102 | T1110 | Multiple Failed Authentication Attempts | Documented — Correlation Validated |
| 100103 | T1082 | System Information Discovery | Documented |
| 100104 | T1016 | Network Configuration Discovery | Documented — Current Rule Validation Pending |
| 100106 | T1105 | Ingress Tool Transfer | Documented — Command Pattern Validated |
| 100107 | T1053.005 | Scheduled Task Persistence | Documented — Alert Observed |
| 100108 | T1547.001 | Registry Run Key Persistence | Documented — Rule Match Validation Pending |
| 100109 | T1562.001 | Microsoft Defender Tampering Command Pattern | Documented |

### Published Detection Case Studies

- [T1562.001 — Microsoft Defender Impairment Detection](T1562.001-Defender-Impairment.md)
- [T1082 — System Information Discovery Detection](T1082-System-Information-Discovery.md)
- [T1016 — System Network Configuration Discovery](T1016-Network-Configuration-Discovery.md)
- [T1110 — Brute Force Detection and Event Correlation](T1110-Brute-Force-Detection.md)
- [T1105 — Ingress Tool Transfer Detection](T1105-Ingress-Tool-Transfer.md)
- [T1053.005 — Scheduled Task Persistence Detection](T1053.005-Scheduled-Task-Persistence.md)
- [T1547.001 — Registry Run Key Persistence Detection](T1547.001-Registry-Run-Key-Persistence.md)


### Detection Documentation Approach

Each detection case study will include:

- Detection objective and MITRE ATT&CK mapping
- Log source and relevant Windows Event ID
- Custom Wazuh rule configuration
- Controlled simulation or observed event
- Alert evidence and investigation findings
- Detection limitations and improvements

> Detection alerts indicate matched rule conditions and do not automatically confirm malicious activity.

## Future Documentation

Individual detection rules, test cases, sample alerts, and validation evidence will be added as development continues.
