# SOC and Threat-Hunting Dashboard Notes

## Scope

This note describes the dashboard screenshots and the one-page OpenSearch Dashboards PDF export supplied for the lab. The screenshots represent separate captures and should not be combined into one set of simultaneous measurements.

## SOC – Security Operations Centre dashboard

The custom dashboard contains four KPI panels:

- Total Security Alerts
- High-Severity Alerts
- Critical Security Alerts
- Windows Defender Detections

It also includes a time-series chart, a recent-alerts table, severity distribution, alerts by agent, top detection rules, and top MITRE ATT&CK techniques.

### Observed dashboard snapshots

| Capture | Total alerts | High-severity | Critical | Defender detections |
|---|---:|---:|---:|---:|
| Dashboard screenshot (one capture) | 8,703 | 543 | 177 | 135 |
| Dashboard screenshot (later capture) | 8,381 | 509 | 172 | 135 |
| One-page PDF report export | 8,651 | 533 | Not fully legible in the exported image | 135 |

These values differ because the screenshots and report are separate snapshots and may have been generated at different times or with different underlying refresh states. The critical count in the PDF preview is visually truncated; no exact value is inferred from it.

The dashboard screenshot also shows a recent-alerts table with endpoint, severity, rule ID, detection description, and alert-record count. This is an aggregated table view; it should not be described as a complete chronological incident timeline.

## Threat Hunting dashboard

The supplied Threat Hunting dashboard screenshots show:

- Top 10 alert-level evolution over time, segmented by Wazuh rule level.
- Top 10 MITRE ATT&CK techniques, presented with technique labels.
- Top 5 agents by alert volume.
- Alert evolution for the top 5 agents.

A separate Threat Hunting overview screenshot shows these summary counters for its selected time range:

| Counter | Displayed value |
|---|---:|
| Total alerts | 8,550 |
| Level 12 or above alerts | 173 |
| Authentication failures | 5 |
| Authentication successes | 13 |

These are dashboard counters, not verified counts of unique incidents, compromised hosts, or successful attacks. Authentication events require contextual investigation before drawing conclusions.

## Report supplied

The supplied one-page PDF is titled **OpenSearch Dashboards Reports** and contains an export of the SOC dashboard. It shows total alerts (8,651), high-severity alerts (533), Windows Defender detections (135), and the associated time-series and distribution panels. Its critical-alert metric is clipped in the rendered report, so that figure is intentionally left unspecified here.

## Interpretation and client-facing presentation

The dashboards demonstrate practical monitoring and hunting workflows: alert-volume awareness, severity-based triage, endpoint comparison, detection-rule prioritization, and ATT&CK-oriented investigation pivots.

They do not, on their own, prove incident containment, prevention effectiveness, full telemetry coverage, or a production managed-SOC service. Client demonstrations should use a defined time range, sanitized data, and clearly stated log-source coverage.

## Evidence handling

Store sanitized screenshots under `evidence/screenshots/` and PDF exports under `evidence/reports/`. Use descriptive filenames and keep this note aligned with the actual files committed. Do not publish credentials, tokens, personal information, or sensitive internal network details.
