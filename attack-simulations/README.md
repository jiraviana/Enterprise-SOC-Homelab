# MITRE ATT&CK Simulations

This folder documents controlled adversary technique
simulations performed in my Wazuh Home SOC Lab.

## Objectives

- Simulate suspicious endpoint activity.
- Generate Windows and Linux security telemetry.
- Validate custom Wazuh detection rules.
- Map behaviors to MITRE ATT&CK techniques.
- Document detection evidence and investigation findings.

## Validated Simulation

### T1562.001 — Impair Defenses: Disable or Modify Tools

**Objective:** Detect PowerShell command patterns
associated with disabling Microsoft Defender.

**Endpoint:** Windows11-Lab

**Wazuh Rule ID:** 100109

**Alert Level:** 12

**Test Method:** Controlled PowerShell test string.

**Result:** Wazuh generated a matching alert.

## Planned Documentation

Additional simulations, detection logic, screenshots,
and investigation results will be documented.

## Safety

Testing is restricted to authorized lab systems.
