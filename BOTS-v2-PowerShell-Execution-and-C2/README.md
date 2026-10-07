# BOTS v2 — Obfuscated PowerShell Execution & C2 Activity

Simulated SOC L1 investigation using Splunk Enterprise and the Boss of the SOC v2 dataset.

## Summary

Suspicious PowerShell activity was detected on internal endpoint `venus.frothly.local` (`10.0.1.101`) running under service account `FROTHLY\service3`.
Execution flags revealed defense evasion techniques, including hidden-window mode (`-w 1`) and Base64 command encoding (`-enc`).
Payload deobfuscation identified an in-memory AMSI bypass (`amsiInitFailed`), an RC4 decryption routine, and an outbound retrieval request to external infrastructure at `45.77.65.211:443/admin/get.php`.
Process creation telemetry (Sysmon Event ID 1) confirmed that PowerShell spawned `python.exe dns.py` from `C:\temp\download\`.
Sysmon network telemetry (Event ID 3) confirmed a successful outbound TCP connection from the compromised host to external IP `45.77.65.211:443`, confirming active post-exploitation and Command-and-Control (C2) communication.

## Disposition

HIGH / CRITICAL — Escalated to Tier 2 (L2) / Incident Response (IR)  
Immediate endpoint isolation and perimeter IP blocking recommended.

## Skills Demonstrated

* Splunk SPL querying
* Windows Event Log & Sysmon analysis (Event ID 1 & Event ID 3)
* Endpoint telemetry analysis (Parent-Child process trees)
* Payload deobfuscation & decoding (CyberChef / Base64 / RC4)
* Defense evasion detection (AMSI bypass analysis)
* Command and Control (C2) network correlation
* Indicator of Compromise (IoC) extraction
* L1 incident triage, containment recommendation, and escalation procedures
