
# MITRE ATT&CK T1057 — Process Discovery

**Detection Status:** Alert Evidence Captured | Rule Details Pending Verification

## 1. Overview

This case study documents process discovery activity observed through PowerShell telemetry and Wazuh SIEM in my Enterprise SOC Home Lab.

The objective is to investigate PowerShell commands associated with process enumeration and evaluate how the resulting security telemetry can support detection engineering and SOC investigations.

## 2. MITRE ATT&CK Mapping

| Field | Description |
|---|---|
| Tactic | Discovery |
| Technique | T1057 — Process Discovery |
| Platform | Windows |
| Telemetry | PowerShell logging |
| SIEM | Wazuh |
| Detection Focus | PowerShell-based process discovery activity |

Process discovery allows a user or attacker to enumerate running processes and identify applications, security tools, and other active software.

Because process enumeration also occurs during legitimate administration and troubleshooting, the surrounding context must be evaluated before determining whether activity is suspicious.

## 3. Detection Objective

Identify PowerShell activity associated with process enumeration and make the resulting telemetry available for investigation in Wazuh.

The investigation focuses on:

- PowerShell command content
- User and endpoint context
- Event timestamps
- Available parent process or execution context
- Related security alerts
- Potentially suspicious follow-on activity

## 4. Detection Evidence

### Wazuh Detection Evidence

![MITRE T1057 PowerShell Process Discovery](../screenshots/MITRE-T1057-PowerShell-Process-Discovery-Wazuh.jpeg)

### Additional Investigation Evidence

![MITRE T1057 Full Detection Evidence](../screenshots/MITRE-T1057-PowerShell-Detection-Full-Evidence.jpeg)

## 5. SOC Investigation Workflow

1. Identify the PowerShell activity associated with the alert.
2. Review the command or script-block content.
3. Identify the affected endpoint and user account.
4. Check the event timestamp and related activity.
5. Determine whether the command is consistent with authorized administration or controlled lab testing.
6. Correlate the activity with other available endpoint telemetry.
7. Document the investigation findings and any required response actions.

## 6. Detection Validation

The screenshots provide supporting evidence for the PowerShell process discovery investigation.

The following details require confirmation against the underlying Wazuh alert and detection rule before the case study can be marked fully validated:

- Exact Wazuh rule ID and severity
- Exact PowerShell command or expression detected
- Source Windows Event ID
- Whether the alert originated from a custom rule or an existing Wazuh rule
- Reproducibility of the detection during a controlled test

An alert associated with process discovery does not independently establish malicious activity or compromise.

## 7. Future Improvements

- Verify and document the exact detection rule.
- Reproduce the detection through controlled testing.
- Add relevant alert fields and detection logic.
- Tune the rule to distinguish routine administrative activity from potentially suspicious process discovery.
- Correlate PowerShell events with Sysmon process creation telemetry where available.

## Conclusion

This case study documents the investigation of PowerShell-based process discovery activity using Wazuh SIEM.

Further validation of the underlying detection logic and alert fields will strengthen the evidence and support a more complete MITRE ATT&CK-aligned detection engineering case study.
