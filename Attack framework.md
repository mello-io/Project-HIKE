# Attack Framework & Detection Mapping

Project HIKE – MITRE ATT&CK Coverage

This document maps the adversary techniques executed during Project HIKE to blue team detections, telemetry sources, and defensive outcomes.
It serves as a detection validation reference for SOC operations, purple-team exercises, and future tuning.

<hr>

## 🎯 Frameworks Used

- MITRE ATT&CK (Enterprise)
- Lockheed Martin Cyber Kill Chain
- Wazuh SIEM Detection & Correlation

<hr>

## 🧠 Attack–Detection Matrix

| Kill Chain Phase |	MITRE Technique |	Technique ID |	Attack Description |	Detection Source | Detection Outcome |
|-----------------|-------------------|-------------|----------------------|------------------|-------------------|
| Reconnaissance |	Network Service Scanning | T1046 |	Enumerated exposed services and hosts |	Firewall logs, Endpoint logs |	Detected via abnormal connection attempts |
| Reconnaissance |	Account Discovery |	T1087 |	Enumerated domain and local users |	Windows Security Logs |	Logged and correlated |
| Initial Access |	Brute Force |	T1110 |	Password spraying & brute-force attempts |	Wazuh agent (Event ID 4625) |	High-fidelity alert generated |
| Credential Access |	Kerberoasting |	T1558.003 |	Requested service tickets for offline cracking |	Domain Controller logs |	Detected via abnormal ticket requests |
| Credential Access |	Credential Dumping |	T1003 |	Attempted access to credential material |	Endpoint telemetry |	Logged; blocked by system controls |
| Discovery |	System Information Discovery |	T1082 |	Collected OS and system details |	Endpoint logs |	Logged (low severity) |
| Discovery |	Network Share Discovery |	T1135 |	Enumerated SMB shares |	Windows logs, network logs |	Logged and correlated |
| Lateral Movement |	Remote Services (RDP) |	T1021.001 |	Attempted movement via RDP |	Firewall + Windows logs |	Detected and audited |
| Lateral Movement |	SMB/Windows Admin Shares |	T1021.002	| Lateral movement via admin shares |	Endpoint + DC logs |	Partial detection |
| Impact |	Account Lockout |	T1531 |	Triggered lockouts from failed auth |	Domain Controller logs |	Alerted, confirmed |

<hr>

## 🔵 Blue Team Telemetry Sources

- Wazuh Agents
  - Windows Security Logs
  - Sysmon-style process visibility
- Domain Controller Logs
- Palo Alto Firewall Logs
- VPN & Jump Server Access Logs

<hr>

## 📊 Detection Effectiveness Summary

| Category |	Status |
|---------|----------|
| Credential Attacks |	✅ Strong detection |
| Brute Force	| ✅ High confidence |
| Lateral Movement |	⚠ Partial visibility |
| Reconnaissance |	⚠ Logged, low severity |
| Impact Events	| ✅ Clear detection |

<hr>

## 🔍 Observations & Gaps

- Reconnaissance techniques generated logs but lacked alert prioritization
- Lateral movement visibility depended on log correlation timing
- Firewall segmentation effectively constrained attack paths
- VPN and jump server controls significantly reduced exposure

<hr>

## 🛠️ Defensive Improvements Identified

- Add rule tuning for low-and-slow recon activity
- Introduce detection scoring for chained techniques
- Expand ATT&CK coverage for persistence techniques

<hr>

## 🧩 Operational Value

This framework enables:
- SOC analyst training
- Detection engineering validation
- Purple team exercises
- Audit and control testing
- Repeatable adversary simulation

<hr>

## 📁 File Relationship

- ` README.md ` → Architecture, scope, outcomes
- ` attack-framework.md ` → Execution, detection, validation

Together, these documents represent a complete security engineering lifecycle artifact.
