# 🛡️ Elastic Home SOC Lab

## Overview

This project documents a Home Security Operations Centre (SOC) lab built using the Elastic Stack.

The purpose of the project was to develop practical SOC analyst and detection engineering skills by building a virtualised security monitoring environment, generating controlled attack traffic, analysing security events, and creating detection rules.

The lab provided hands-on experience with:

- SIEM deployment and administration
- Centralised log collection
- Security event analysis
- Threat detection
- Attack simulation
- Incident investigation
- Detection engineering
- Network monitoring
- MITRE ATT&CK mapping

---

## Lab Environment

| Component | Technology |
| --- | --- |
| SIEM | Elastic Stack |
| Server | Ubuntu Server |
| Attack Machine | Kali Linux |
| IDS | Suricata |
| Log Collection | Elastic Agent |
| Agent Management | Fleet Server |
| Security Monitoring | Elastic Security |
| Attack Tools | Hydra, Nmap |

---

## Architecture

The lab used Kali Linux as the attack system and Ubuntu Server as the primary monitored infrastructure.

Ubuntu Server hosted the Elastic Stack components used for log collection, analysis, and security monitoring.

Attack activity generated from Kali Linux was captured by the monitored environment and analysed using Elastic Security.

Architecture and detection-flow diagrams are available in the [`diagrams`](diagrams/) directory.

---

## Detection Scenario

The primary detection scenario implemented in the lab focused on SSH brute-force activity.

The general attack and detection process was:

**Kali Linux → Hydra Attack → SSH Authentication Failures → Linux Authentication Logs → Elastic Agent → Elasticsearch → Kibana / Elastic Security → Detection Rule → Security Alert**

Hydra was used from Kali Linux to generate controlled SSH authentication failures against the Ubuntu environment.

These authentication events were collected by Elastic Agent and ingested into Elasticsearch, where they could be investigated through Kibana.

A custom detection rule was then used to identify the simulated brute-force behaviour and generate a security alert.

---

## MITRE ATT&CK Mapping

The SSH brute-force detection scenario was mapped to the MITRE ATT&CK framework:

- **Tactic:** Credential Access
- **Technique:** Brute Force
- **MITRE ATT&CK ID:** T1110

This demonstrates how security detections can be associated with recognised adversary techniques.

---

## Suricata IDS

Suricata was installed and configured within the lab to provide network-based monitoring capabilities.

The Suricata component demonstrates how network intrusion detection can complement endpoint and authentication telemetry within a SOC environment.

Additional Suricata documentation is available in the [`suricata`](suricata/) directory.

---

## Project Structure

```text
home-soc-elastic/
│
├── detections/      # Detection rule documentation
├── diagrams/        # Architecture and detection-flow diagrams
├── docs/            # Technical project documentation
├── screenshots/     # Screenshots and implementation evidence
├── suricata/        # Suricata IDS documentation
├── .gitignore
├── .gitattributes
└── README.md