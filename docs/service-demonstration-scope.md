# Client Demonstration Scope

This document describes realistic demonstrations that can be delivered from the current lab after the relevant end-to-end checks are completed. It is not a claim of an existing managed security service.

## Demonstration options

### 1. Endpoint telemetry visibility review
- Show Wazuh agent onboarding and endpoint health.
- Review selected Windows event sources such as Sysmon and PowerShell.
- Explain which events are locally generated, collected, received and alerted.
- Deliver a short configuration and visibility findings note.

### 2. SIEM onboarding proof of concept
- Agree a small, authorized test scope.
- Connect a test endpoint to Wazuh.
- Validate selected event sources and document ingestion evidence.
- Demonstrate dashboard searches and a small number of tested detections.

### 3. Network IDS visibility proof of concept
- Demonstrate Suricata interface selection, rule loading and EVE event generation.
- Validate that the sensor sees only the traffic within the agreed capture path.
- Demonstrate event forwarding only after manager-side ingestion is verified.

## Example deliverables

- Scope and assumptions.
- High-level architecture diagram.
- Sanitized configuration summary.
- Evidence-backed validation results.
- Gaps, risks and prioritized next steps.
- Handover notes.

## Explicit exclusions unless separately agreed and properly resourced

- 24/7 monitoring or incident response.
- Guaranteed prevention, detection coverage or regulatory compliance.
- Production deployment, penetration testing, malware analysis, or access to systems outside written scope.
- Service-level guarantees or emergency response commitments.

## Before any engagement

Obtain written authorization, identify assets and owners, agree test windows and stop conditions, establish data retention and deletion rules, and define escalation contacts. Never use this lab against a third-party system without permission.
