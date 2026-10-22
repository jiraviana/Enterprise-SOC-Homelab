# MITRE ATT&CK Simulations

**Project Status:** Ongoing Development | Active Testing

## Overview

This folder documents controlled security simulations performed in my Wazuh Enterprise SOC Home Lab. The purpose is to evaluate detection coverage, validate custom Wazuh rules, and practice security alert investigation using the MITRE ATT&CK framework.

All tests are conducted within an authorized lab environment. Simulation results and supporting evidence are documented as testing progresses.

## Simulation Tracking

| Technique | Detection Scenario | Status | Evidence |
|---|---|---|---|
| T1562.001 | Microsoft Defender real-time protection disable command pattern | Detection validated | [Case Study](../detection-rules/T1562.001-Defender-Impairment.md) |

## Simulation 01 — MITRE ATT&CK T1562.001

**Technique:** Impair Defenses: Disable or Modify Tools

**Objective:** Validate whether a custom Wazuh detection identifies PowerShell script-block content containing a command pattern associated with disabling Microsoft Defender real-time protection.

### Lab Environment

- SIEM: Wazuh 4.14.8
- Endpoint: Windows11-Lab
- Telemetry: PowerShell Script Block Logging, Windows Event ID 4104
- Custom Rule ID: 100109
- Alert Severity: Level 12

### Test Methodology

1. Configured a custom Wazuh detection for the relevant PowerShell command pattern.
2. Used a controlled PowerShell test string containing the pattern.
3. Reviewed the resulting security event in Wazuh.
4. Confirmed the rule ID, severity, endpoint, and MITRE ATT&CK mapping.

### Observed Result

Wazuh generated a Level 12 alert for Rule ID 100109, mapped to MITRE ATT&CK T1562.001.

**Validation scope:** This test confirms command-pattern detection. It does not confirm that Microsoft Defender real-time protection was disabled.

### Detection Evidence

![T1562.001 Detection Evidence](../screenshots/MITRE-T1562.001-Defender-Tampering-Detection.png.jpeg)

### Detailed Documentation

[View T1562.001 Detection Engineering Case Study](../detection-rules/T1562.001-Defender-Impairment.md)

## Future Simulation Work

Additional MITRE ATT&CK techniques will be selected, simulated, tested, and documented as the lab develops. Each completed scenario will include its test objective, telemetry source, detection result, evidence, and limitations.

## Disclaimer

This project is for authorized defensive security testing and education. The environment remains under active development.
