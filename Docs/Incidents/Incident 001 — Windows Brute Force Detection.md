# Incident 001 — Windows Brute Force Detection

## Executive Summary

A controlled brute-force authentication attack was simulated against a Windows endpoint monitored by Wazuh SIEM. The objective was to validate endpoint visibility, log collection, and alert generation.

**Status:** Closed

**Severity:** Medium

## Environment

| Item | Value |
|---|---|
| SIEM | Wazuh 4.14.1 |
| Endpoint | Windows 11 |
| Agent | Ash-PC |
| Manager | Ubuntu Server (Docker) |

## Attack Simulation

Ten failed interactive logon attempts were performed using a non-existent user account.

**Command**

```powershell
runas /user:FakeUser cmd
```

## Detection

| Field | Value |
|---|---|
| Windows Event ID | 4625 |
| Wazuh Rule | 60122 |
| Rule Level | 5 |
| Logon Type | 2 |
| Username | FakeUser |

## MITRE ATT&CK

| Tactic | Technique |
|---|---|
| Credential Access | T1110 – Brute Force |

## Analyst Notes

The authentication attempts targeted a non-existent account (`FakeUser`). Wazuh successfully collected the Windows Security events and generated authentication failure alerts, confirming that endpoint monitoring and SIEM ingestion were functioning correctly.

## Outcome

- Wazuh detected all failed authentication attempts.
- Endpoint logging was verified.
- No successful compromise occurred.
- This activity was performed as a controlled laboratory exercise.