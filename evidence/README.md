# Evidence folder

Add only sanitized, approved evidence that supports a specific claim in the documentation.

## Suggested evidence checklist

- [ ] Wazuh dashboard showing the lab agent connected (hide usernames and sensitive host details).
- [ ] Wazuh agent log showing the Sysmon channel is monitored.
- [ ] Suricata configuration test result showing successful validation.
- [ ] Sanitized EVE DNS / flow event sample.
- [ ] Defender Event 1116 and 1117 details with personal and machine identifiers removed.
- [ ] Manager-side raw event evidence when Defender and Suricata ingestion are verified.

## Evidence quality

For each item, record the date, source system, validation step and what the evidence proves. State what it does not prove. Do not use a screenshot of local configuration as proof of manager-side ingestion.

Do not commit raw EVTX files, full logs, packet captures, secrets or unredacted personal data.
