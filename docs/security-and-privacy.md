# Security, Privacy and Responsible Testing

## Lab boundaries

- Test only systems you own or have explicit written authorization to assess.
- Keep experimental endpoints isolated from production and third-party networks.
- Define the permitted hosts, time window, techniques and stop conditions before a demonstration.
- Do not run untrusted payloads on a daily-use workstation.

## Data hygiene before publishing

Never commit:
- Passwords, tokens, private keys, API keys, connection strings or recovery codes.
- Raw EVTX files, full EVE JSON logs, packet captures or unfiltered endpoint telemetry.
- Personal information, usernames, email addresses, hostnames or client identifiers that have not been approved for disclosure.
- Internal network diagrams or addresses that reveal a real client environment.

Use sanitized screenshots and short synthetic examples. Review every file and image before pushing it to a public repository.

## Defensive control preservation

Do not disable antivirus, tamper protection, logging, firewalls or other security controls merely to make a demonstration succeed. If a test is blocked, document that result and use a safe alternative.

## Service engagement safeguards

Any client-facing work requires written authorization, agreed scope, data handling and retention terms, escalation contacts, and a clear statement of deliverables and exclusions. A lab proof of concept is not a production security assessment or managed SOC service.
