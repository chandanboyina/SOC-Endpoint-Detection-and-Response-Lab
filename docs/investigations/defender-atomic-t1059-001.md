# Investigation: Defender detection during a PowerShell test

## Summary

A controlled Atomic Red Team test associated with MITRE ATT&CK **T1059.001 – PowerShell** was attempted on the Windows lab endpoint. Microsoft Defender detected and removed a payload associated with the test. The Atomic test did not complete successfully.

## Endpoint evidence

| Field | Observation |
|---|---|
| Detection event | Windows Defender Operational, Event ID 1116 |
| Local timestamp | 2026-11-20 23:09:23 (endpoint local time) |
| Threat name | `Trojan:Win32/Powessere.K` |
| Threat ID | `2147734747` |
| Severity | Severe |
| Remediation event | Event ID 1117 |
| Remediation timestamp | 2026-11-20 23:09:44 (endpoint local time) |
| Action | `Remove` |
| Result | `No additional actions required`; error `0x00000000` |

The local event details included the encoded PowerShell command used by the test.

## Test outcome and limitations

- The attempted command was `Invoke-AtomicTest T1059.001 -TestNumbers 10`, described as a PowerShell fileless script execution test.
- The test invocation returned an access-denied error from the process invocation script.
- The expected marker file `C:\Windows\Temp\art-marker.txt` and registry artifact were not present afterwards.
- Defender detection and remediation are verified locally. The evidence does not establish the exact causal mechanism behind the access-denied exception.
- Wazuh dashboard searches in `wazuh-alerts-*` did not show these event IDs during the check. Manager-side raw receipt and indexing are not confirmed.

## Investigation workflow

1. Review Defender Operational events 1116 and 1117 on the endpoint.
2. Correlate detection time, threat name, threat ID and remediation result.
3. Check whether expected test artifacts exist; do not assume the test completed.
4. Check Wazuh raw event storage and decoder/rule processing before claiming SIEM ingestion.
5. Preserve sanitized evidence and record the test limitation.

## Safety

Do not rerun suspicious payloads outside an isolated, authorized lab. Do not disable Defender, tamper protection, or add exclusions to force execution. Prefer benign telemetry validation when troubleshooting ingestion.
