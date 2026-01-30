# Project HIKE

Hybrid Infrastructure Kill-chain Evaluation

> An end-to-end on-prem enterprise security lab designed to simulate real-world adversary behavior and validate defensive detection and response using SysSDLC principles, MITRE ATT&CK, and SOC tooling.

<hr>

## 📌 Project Overview

Project HIKE is a structured cybersecurity engineering initiative focused on designing, deploying, attacking, and defending a segmented enterprise infrastructure. The project applies System Security Development Lifecycle (SysSDLC) principles to validate how modern blue-team controls detect and respond to realistic red-team techniques.

The lab emulates a production-like environment including endpoints, servers, VPN access, firewall enforcement, red team tooling, and SOC monitoring. Enabling full kill-chain visibility from reconnaissance to post-exploitation.

<hr>

## 🎯 Objectives

- Build a production-like on-prem enterprise environment
- Enforce network segmentation and controlled access paths
- Simulate adversary behavior using Kali & Caldera
- Perform defensive visibility, detection and analysis with Wazuh
- Map activity to MITRE ATT&CK and LM Cyber Kill Chain
- Validate security controls across network, endpoint, and identity layers
- Document outcomes for operational and audit readiness

<hr>

## 🧠 SysSDLC Alignment

| SysSDLC Phase |	Implementation in Project HIKE |
|---------------|--------------------------------|
| Planning | Threat modeling, architecture & network planning, attack surface definition |
| Design | Network segmentation, trust boundaries, firewall policy design |
| Build |	ESXi deployment, endpoint provisioning, Wazuh & Caldera deployment |
| Test |	Red team exploit preparation, detection validation, log verification |
| Deploy |	VPN access, jump server operations, agent rollout, SOC monitoring, red team ops |
| Operate |	Continuous log analysis & correlation, rule tuning, incident validation |
| Review |	Kill-chain mapping, detection gaps, defensive effectiveness assessment |

<hr>

## 🏗️ Architecture & Env. Formation

[pic]

Infrastructure Components;

Endpoint Subnet
- Windows 10 endpoint
- Windows 11 endpoint
- Wazuh agents deployed on all endpoints
<br>

Server & Management Layer
- ESXi Server (virtualized workloads)
- ESXi Host (internal compute)
- Web Server (application-facing services)
- SQL Server (data layer)
<br>

Network Security
- Palo Alto Firewall enforcing inter-subnet access
- Internal routing & traffic inspection
- Explicit ingress/egress control between zones
<br>

Access Control
- VPN (0-Tier) for remote administrative access
- RDP Jump Server for controlled internal access
- No direct endpoint exposure from external networks
<br>

Red Team Subnet
- Kali Linux attack host
- MITRE Caldera for adversary emulation
<br>

Blue Team Subnet
- Wazuh Server (SIEM)
- SOC workstation
- Centralized logging and alert correlation
<br>

> Design Principle: All attack paths are forced through firewall-controlled choke points to ensure full observability.


<hr>

## 🔴 Red Team Operations

Tools & Techniques
- Kali Linux
- MITRE Caldera
- Manual adversary emulation

Attack Scenarios
- Network & Host reconnaissance
- Authentication Brute-force attacks
- Kerberoasting
- Credential access
- Lateral movement
- Active Directory enumeration

All attacks were executed against controlled assets conditions to ensure complete telemetry capture for defensive analysis.

<hr>

## 🔵 Blue Team Operations

Detection & Monitoring
- Wazuh SIEM
- Endpoint agents on Windows hosts
- Centralized log ingestion and correlation

Analysis Frameworks
- MITRE ATT&CK
- Lockheed Martin Cyber Kill Chain

Validation
- Firewall enforcement verification
- VPN access control testing
- Log integrity and visibility checks
- Alert fidelity and false-positive review

<hr>

## 📊 Outcomes & Results

- Successfully mapped real adversary behavior to MITRE ATT&CK framework [TTP]
- Validated end-to-end log visibility across endpoints and network
- Verified firewall and segmentation effectiveness
- Identified detection strengths and reduced coverage gaps
- Demonstrated how defensive controls disrupt attack progression
- Produced actionable findings reciprocating to SOC analysis using real attack telemetry

<hr>

## 🛠️ Technologies Used

- Virtualization: ESXi
- Firewall: Palo Alto Networks
- Red Team: Kali Linux, MITRE Caldera
- Blue Team: Wazuh SIEM
- Operating Systems: Windows 10, Windows 11, Windows Server 2022
- Frameworks: MITRE ATT&CK, LM Cyber Kill Chain
- Networking: VPN, segmented subnets, jump server architecture

<hr>

## 🧩 Skills Gained

- Enterprise network design & segmentation
- SysSDLC-driven security engineering
- Threat modeling and adversary emulation
- SOC operations and SIEM analysis
- Firewall rule design and policy validation
- Incident detection, tuning and kill chain mapping
- Technical documentation and reporting

<hr>

## 🌍 Real-World Relevance

Project HIKE mirrors how enterprise security teams:
- Validate defensive posture
- Test SOC detection capabilities
- Prepare for audits and control reviews
- Train analysts on realistic attack scenarios
- Align controls with industry frameworks

The lab architecture and workflow can be directly adapted for:
- Internal security testing
- SOC analyst training
- Internal purple team exercises
- Compliance and control validation
- Developing detection engineering pathways

<hr>

## 📈 Future Enhancements

- Additional ATT&CK technique coverage
- Automated detection scoring
- Integration with XDR platforms
- Cloud-hybrid expansion

<hr>

## 👤 Collaboration & Contributions

This project is designed, implemented, operated, and documented under the leadership of Dr. Victor Monga and conducted by Derick Dmello and Kamran Memarzia, focusing on security engineering, defensive analysis, and operational realism.

<hr>

