# BOTS v2 — Targeted Spear-Phishing Campaign & Initial Execution Triage
Simulated SOC L1 investigation using Splunk Enterprise and the Boss of the SOC v2 dataset.

## Summary

A targeted spear-phishing campaign was detected against multiple Froth.ly corporate mailboxes (`fyodor@froth.ly`, `btun@froth.ly`, `abungstein@froth.ly`, and `klagerfield@froth.ly`). Inbound network telemetry (`stream:smtp`) revealed messages originating from external relay IP `185.83.51.21` (`smtp12.ymlpsvr.com`) spoofing `jsmith@urinalysis.com` with the subject `Invoice`. The emails delivered a password-protected ZIP archive (`invoice.zip`, password: `912345678`) configured as `application/octet-stream` to evade automated perimeter content filtering. Inspection of security gateway alerts identified the payload as `O97M/Donoff!grn` / `Trojan/ZFEJ-2`. Process creation telemetry (Sysmon Event ID 1) confirmed initial execution on workstation `wrk-btun.frothly.local` (`10.0.2.107`), where user `FROTHLY\billy.tun` extracted and opened `invoice.doc` via `WINWORD.EXE` (PID `4208`). Subsequent host and network analysis yielded zero child process creation (no `cmd.exe` or `powershell.exe`), zero secondary file drops, and no outbound C2 traffic under PID `4208`, confirming that Office macro protection successfully prevented payload detonation.

## Disposition

MEDIUM — Resolved / Closed at Tier 1 (L1)
Perimeter blocking of source IP `185.83.51.21` and sender domain `urinalysis.com`, tenant-wide mailbox purge of remaining archives, and user security-awareness coaching recommended. No host isolation required.

## Skills Demonstrated

* Splunk SPL querying
* Network stream analysis (SMTP payload inspection & MIME boundary decoding)
* Base64 decoding & deobfuscation of perimeter security alerts
* Windows Event Log & Sysmon analysis (Event ID 1 & Event ID 11)
* Host telemetry correlation (Parent-Child process lineage verification)
* Defense evasion identification (Password-protected archives & MIME type spoofing)
* Negative finding validation (Confirming absence of post-exploitation activity)
* Indicator of Compromise (IoC) extraction & email header forensics
* SOC L1 incident documentation, reporting, and closure workflow

## Evidence

See the [`Evidence/ directory.`](./Evidence/)

## Report

See [`SOC-2026-002-Phishing-Incident-Report.pdf`](./SOC-2026-002-Phishing-Incident-Report.pdf).
