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

## Future Documentation

Individual detection rules, test cases, sample alerts, and validation evidence will be added as development continues.
