# SOC and Threat-Hunting Dashboard Evidence

## Evidence set

The repository contains four dashboard screenshots under [evidence/screenshots](../evidence/screenshots/):

- [SOC dashboard overview](../evidence/screenshots/soc-dashboard-overview.jpeg)
- [SOC dashboard analytics](../evidence/screenshots/soc-dashboard-analytics.jpeg)
- [Threat Hunting overview](../evidence/screenshots/threat-hunting-overview.jpeg)
- [Threat Hunting analytics](../evidence/screenshots/threat-hunting-analytics.jpeg)

The event export is stored at [evidence/reports/windows-defender-events-export.csv](../evidence/reports/windows-defender-events-export.csv).

## SOC – Security Operations Centre dashboard

The custom SOC dashboard combines four KPI panels — Total Security Alerts, High-Severity Alerts, Critical Security Alerts, and Windows Defender Detections — with:

- Security Alerts Over Time
- Recent Security Alerts table
- Severity Distribution
- Alerts by Agent
- Top 10 Detection Rules
- Top MITRE ATT&CK Techniques

## Wazuh Threat Hunting dashboard

The two Threat Hunting screenshots show:

- Top 10 Alert Level Evolution, with Wazuh rule levels plotted over time.
- Top 10 MITRE ATT&CKs, presented as technique names.
- Top 5 agents.
- Alert evolution for the top 5 agents.

The overview screenshot displays these counters for its selected **Last 7 days** view:

| Counter | Displayed value |
|---|---:|
| Total | 8,550 |
| Level 12 or above alerts | 173 |
| Authentication failure | 5 |
| Authentication success | 13 |

These are dashboard counters, not unique incident counts or proof of successful/failed compromise attempts.

## Supplied report files and exports

### OpenSearch SOC dashboard report

The supplied file is a one-page PDF titled **OpenSearch Dashboards Reports**. It exports the SOC dashboard and shows total alerts (8,651), high-severity alerts (533), Windows Defender detections (135), the alert trend, severity distribution, alerts by agent, top detection rules, and top MITRE ATT&CK techniques. The Critical KPI is clipped in the rendered report. The PDF binary has not yet been committed to this repository; see the repository README for the current downloadable evidence link status.

### Wazuh agent threat-hunting report

The supplied Wazuh PDF is a nine-page **Threat hunting report** for agent **PC1_W11** (agent ID **002**), Wazuh **v4.14.9**, managed by **wazuh-server**. It identifies Windows 11 Pro as the operating system and uses the query:

`manager.name: wazuh-server AND agent.id: 002`

The report's displayed time window is **2026-11-18T19:51:07 to 2026-11-25T19:51:07**. Its pages include alert-group evolution, alerts, top 5 alerts, top 5 rule groups, top 5 PCI DSS requirements, and multi-page alert summaries with rule IDs, descriptions, levels, and counts. The PDF binary has not yet been committed to this repository.

### Windows Defender events CSV

The committed CSV contains **58 records** for agent **PC1_W11** (agent ID **2**, IP shown in the export as **192.168.200.128**). All rows are Windows Defender **Event ID 1116**, Wazuh **rule ID 62123**, rule level **12**. It contains **57 unique detection IDs** and **57 unique threat names**; one threat/detection identifier appears twice. All records show action name **Not Applicable** and additional actions **No additional actions required**. These fields do not prove that Defender remediated the detected items.

## Interpretation and client-facing use

These artifacts demonstrate monitoring and investigation workflows: alert-volume awareness, time-series review, endpoint comparison, severity distribution, rule prioritization, ATT&CK-oriented pivots, agent-scoped hunting, and exportable evidence review.

They do not independently prove incident containment, prevention effectiveness, complete telemetry coverage, or production managed-SOC capability. For a client demonstration, use an agreed time window, sanitized evidence, documented log-source coverage, and explicit authorization.

## Evidence handling

Screenshots are stored under `evidence/screenshots/`; the CSV export is stored under `evidence/reports/`. PDF source files were supplied in the conversation but are not currently present in the GitHub tree. Do not publish credentials, tokens, personal information, or sensitive internal network details.
