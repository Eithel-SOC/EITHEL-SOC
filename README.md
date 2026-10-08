# Hi, I'm Eithel Belalcazar

### Junior SOC Analyst | Blue Team | Cybersecurity

I'm a cybersecurity professional transitioning into a **Junior SOC Analyst / SOC L1** role, with a focus on security monitoring, incident triage, log analysis, and investigation.

I recently completed **Blue Team Level 1 (BTL1)**, gaining hands-on experience across threat intelligence, digital forensics, network analysis, SIEM investigation, and incident response workflows.

My current focus is turning that knowledge into practical SOC experience through realistic investigations, incident documentation, and hands-on labs.

---

## What I Work With

**SIEM & Log Analysis**

* Splunk Enterprise
* SPL
* HTTP and Windows event analysis

**Security Investigation**

* Alert triage
* IOC identification
* Network traffic analysis
* IDS investigation
* Incident correlation
* Evidence-based escalation

**Blue Team Tools**

* Wireshark
* Autopsy
* TheHive
* Suricata
* windows/linux

**Platforms & Environments**

* Windows
* Linux
* TryHackMe
* Boss of the SOC (BOTS)

---

## Certification

**Blue Team Level 1 (BTL1)**
Security Blue Team

Hands-on training covering:

* Threat Intelligence
* Digital Forensics
* SIEM investigation
* Network analysis
* Incident response
* Security investigation workflows

---

## SOC Portfolio

This repository contains simulated SOC investigations based on realistic datasets and scenarios.

Each case is documented from an analyst perspective, including:

**Alert → Investigation → Evidence → Assessment → Disposition**

### Current Cases

**BOTS v1 — Web Vulnerability Scanning**
Investigation of automated web vulnerability scanning using Splunk and Suricata data.

The investigation identified Acunetix WVS activity, correlated web attack detections, and requests targeting potentially sensitive system files. Further analysis determined that the apparent file access was consistent with a Soft 404 response, allowing the incident to be resolved at L1 without evidence of compromise.

→ [`BOTS-v1-Web-Vulnerability-Scanning/`](./BOTS-v1-Web-Vulnerability-Scanning/)

**BOTS v2 — Obfuscated PowerShell Execution & C2 Activity** Investigation of post-exploitation activity, defense evasion, and outbound C2 communication using Splunk and Sysmon telemetry.

The investigation confirmed code execution on an internal host via an obfuscated, Base64-encoded PowerShell command under a service account. Payload deobfuscation revealed in-memory AMSI bypass routines and external download staging, followed by secondary execution of a Python script from a temporary directory. Correlation with Sysmon network events confirmed successful outbound communication to external C2 infrastructure, resulting in immediate containment recommendations and escalation to L2/IR.

→ [`BOTS-v2-PowerShell-Execution-and-C2/`](./BOTS-v2-PowerShell-Execution-and-C2/)

**BOTS v2 — Targeted Spear-Phishing Campaign** Investigation of an inbound malicious email campaign and endpoint execution triage using Splunk.

The investigation identified a spear-phishing campaign delivering a password-protected macro-enabled Word document to corporate mailboxes. Further endpoint telemetry analysis confirmed the targeted user opened the document, but Office security controls successfully prevented payload detonation, allowing the incident to be resolved at L1 as an unsuccessful intrusion attempt without evidence of compromise.

→ [SOC-2026-002-Phishing-Incident-Report/](./SOC-2026-002-Phishing-Incident-Report)

More investigations will be added as I continue building practical SOC experience.

---


## About This Repository

The projects in this repository are **training and portfolio work**, not professional client engagements.
All investigations are performed in authorized lab environments or public datasets and are documented to reflect real-world SOC workflows as closely as possible.

---

## Contact

**LinkedIn:** [Your LinkedIn URL]
**Email:** [ebelalcazar99@gmail.com]

I'm currently interested in **Junior SOC Analyst / SOC L1 opportunities**.


