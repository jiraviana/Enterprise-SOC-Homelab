
# MITRE ATT&CK T1057 — Process Discovery

**Detection Status:** Alert Generation Validated | Rule Logic Review Pending

## 1. Overview

This case study documents the detection and investigation of PowerShell-based process discovery activity using Wazuh SIEM in my Enterprise SOC Home Lab.

The objective is to identify process enumeration commands, examine the associated Windows security telemetry, and validate alert generation mapped to MITRE ATT&CK T1057 — Process Discovery.

Process discovery can be used by adversaries to identify running applications, security tools, and other software. However, the same activity is common during legitimate system administration and troubleshooting, making contextual investigation essential.

## 2. MITRE ATT&CK Mapping

| Field | Description |
|---|---|
| Tactic | Discovery |
| Technique | T1057 — Process Discovery |
| Platform | Windows |
| Telemetry Source | PowerShell Operational Logs |
| SIEM | Wazuh |
| Detection Focus | PowerShell-based process enumeration |

## 3. Detection Evidence

### Wazuh Detection Evidence

The Wazuh Threat Hunting dashboard displayed alerts associated with PowerShell process discovery activity on the monitored Windows endpoint.

![MITRE T1057 PowerShell Process Discovery](../screenshots/MITRE-T1057-PowerShell-Process-Discovery-Wazuh.jpeg)

### Additional Investigation Evidence

Additional captured evidence supports the review of PowerShell process discovery activity and its associated Wazuh alerts.

![MITRE T1057 Full Detection Evidence](../screenshots/MITRE-T1057-PowerShell-Detection-Full-Evidence.jpeg)

## 4. SOC Investigation Workflow

The investigation workflow covers the following activities:

1. Identify the PowerShell process discovery alert in Wazuh Threat Hunting.
2. Review the detection rule, MITRE ATT&CK mapping, and alert details.
3. Examine the PowerShell script-block content.
4. Identify the affected endpoint and available user context.
5. Review timestamps, repeated events, and related activity.
6. Assess whether the commands are consistent with authorized administration or controlled testing.
7. Correlate with additional endpoint telemetry where available.
8. Document the findings and validation limitations.

## 5. Detection Validation Results

Wazuh Threat Hunting displayed PowerShell process discovery alerts from the `Windows11-Lab` endpoint on October 19, 2026.

### Observed Alert Details

| Field | Observed Value |
|---|---|
| MITRE ATT&CK Technique | T1057 — Process Discovery |
| Wazuh Rule ID | 91815 |
| Rule Description | PowerShell executing process discovery |
| Endpoint | Windows11-Lab |
| Log Channel | Microsoft-Windows-PowerShell/Operational |
| Detection Date | October 19, 2026 |
| Dashboard Search Results | 20 matching alert records |
| Validation Status | Alert Generation Validated |

### Observed PowerShell Commands

The following process enumeration commands appeared in the collected script-block telemetry:

```powershell
Get-Process -Name powershell
```

Enumerates running PowerShell processes.

```powershell
Get-Process | Select-Object -First 5 Name, Id
```

Retrieves process names and IDs for the first five returned processes.

### Investigation Findings

The observed events demonstrate that Wazuh generated alerts for PowerShell process enumeration activity and associated them with MITRE ATT&CK T1057.

The dashboard returned 20 matching alert records during the selected search period. These records do not necessarily represent 20 distinct command executions.

**Validation Result: Alert Generation Validated**

The evidence supports detection of the observed commands and centralized visibility through Wazuh Threat Hunting.

### Validation Limitations

The following technical details remain pending verification:

- Exact detection conditions of Wazuh Rule `91815`
- Whether the rule is built-in or custom
- Rule severity level
- Underlying Windows Event ID
- Reproducibility through a separately documented controlled test

The observed commands are not, by themselves, evidence of malicious activity or successful compromise.

## 6. Future Improvements

- Inspect the definition of Wazuh Rule `91815` and document its detection conditions.
- Confirm the source Windows Event ID and rule severity.
- Perform a controlled test to verify reproducibility.
- Correlate PowerShell events with Sysmon process creation telemetry.
- Evaluate additional process discovery commands and potential detection gaps.
- Improve contextual analysis to distinguish legitimate administration from suspicious reconnaissance.

## Conclusion

This case study demonstrates Wazuh SIEM visibility into PowerShell-based process discovery activity on a monitored Windows endpoint.

Alert generation and MITRE ATT&CK T1057 mapping were confirmed through the collected evidence. Further rule-level verification and controlled testing will strengthen the detection engineering assessment.
