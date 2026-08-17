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

```




## Documentation

Detailed documentation and evidence for the project are organised throughout the repository:

- [`detections/`](detections/) — Elastic Security detection rule documentation
- [`diagrams/`](diagrams/) — SOC architecture and attack/detection flow diagrams
- [`docs/`](docs/) — Detailed technical documentation
- [`screenshots/`](screenshots/) — Screenshots showing implementation, testing, logs, dashboards, and alerts
- [`suricata/`](suricata/) — Suricata IDS documentation

---

## Screenshots and Evidence

The repository contains screenshots collected during the implementation and testing of the lab.

These include evidence of:

- Elastic and Fleet configuration
- Elastic Agent operation
- Kali Linux attack activity
- Nmap scanning
- Hydra activity
- Authentication logs
- Kibana event investigation
- Elastic Security detection
- Security alerts
- Suricata operation

See the [`screenshots`](screenshots/) directory for the complete evidence collection.

---

## Skills Demonstrated

This project demonstrates practical experience with:

- Elastic Stack
- Elasticsearch
- Kibana
- Elastic Security
- Elastic Agent
- Fleet Server
- Linux administration
- Kali Linux
- Suricata IDS
- SSH security monitoring
- Log analysis
- SIEM investigation
- Detection engineering
- Hydra
- Nmap
- Attack simulation
- MITRE ATT&CK
- Git and GitHub
- Technical documentation

---

## Limitations

This project was designed as a home SOC lab for learning and demonstrating security monitoring, log analysis, attack simulation, and detection engineering.

As a result, it has several limitations compared with a production SOC environment.

- The environment was virtualised and operated as a small home lab rather than a production network.
- Attack traffic was intentionally generated from Kali Linux in a controlled environment.
- The primary detection scenario focused on SSH brute-force activity.
- Suricata was installed and configured as an IDS, but advanced Suricata detection scenarios were not fully developed or integrated into custom Elastic detection rules.
- The environment contained only a small number of monitored systems compared with an enterprise network.
- High availability, redundancy, long-term log retention, and large-scale infrastructure were outside the scope of the project.
- The lab environment was temporary and is no longer actively running.
- Screenshots and documentation in this repository preserve evidence of the completed implementation and testing.

---

## Future Improvements

Potential improvements to the lab include:

- Creating additional Elastic Security detection rules for different attack techniques.
- Integrating Suricata alerts more extensively with Elastic Security.
- Developing detection scenarios for network reconnaissance such as Nmap scanning.
- Adding Windows security monitoring and Windows-specific detection scenarios.
- Simulating additional attacks from Kali Linux to test detection coverage.
- Creating additional dashboards for authentication failures, network activity, and security alerts.
- Mapping additional detection rules to the MITRE ATT&CK framework.
- Implementing alert severity levels and improved investigation workflows.
- Expanding the environment with additional endpoints and services to better represent an enterprise network.

---

## Project Outcome

The project successfully demonstrated the basic workflow of a small Security Operations Centre:

**Generate activity → Collect telemetry → Analyse events → Detect suspicious behaviour → Generate an alert → Investigate**

The lab provided practical experience building and operating a security monitoring environment using the Elastic Stack and demonstrated how attack activity can be transformed into observable security events and actionable detections.

Although the environment was created for educational purposes, the concepts demonstrated in the project reflect common SOC workflows including centralised logging, SIEM analysis, detection engineering, network monitoring, attack simulation, and security investigation.

The implementation evidence, diagrams, detection documentation, and screenshots have been preserved in this repository as a portfolio record of the completed project.
