#  Elastic Home SOC Lab

## Overview

This project documents my Home Security Operations Centre (SOC) built using the Elastic Stack.

The lab was created to develop practical SOC analyst skills, including:

- Elastic Stack deployment
- Log collection and analysis
- Threat detection
- Attack simulation
- Incident investigation
- Detection engineering

---

## Lab Environment

| Component | Technology |
|-----------|------------|
| SIEM | Elastic Stack |
| Operating System | Ubuntu Server |
| Attack Machine | Kali Linux |
| IDS | Suricata |
| Log Collection | Elastic Agent |
| Detection | Elastic Security |
| Attack Tools | Hydra, Nmap |

---

## Current Features

- Elastic Stack deployment
- Fleet Server
- Elastic Agent
- SSH authentication log collection
- Custom SSH brute-force detection rule
- Kibana dashboards
- Attack simulations using Hydra


## Limitations

This project was designed as a home SOC lab for learning and demonstrating security monitoring, log analysis, attack simulation, and detection engineering. As a result, it has several limitations compared with a production SOC environment.

- The entire environment was virtualised and operated as a small home lab rather than a production network.
- Attack traffic was intentionally generated from Kali Linux in a controlled environment.
- The primary detection scenario focused on SSH brute-force activity.
- Suricata was installed and configured as an IDS, but advanced Suricata detection scenarios were not fully developed or integrated into custom Elastic detection rules.
- The environment contained only a small number of monitored systems compared with an enterprise network.
- High availability, redundancy, long-term log retention, and large-scale infrastructure were outside the scope of the project.
- The lab environment was temporary and is no longer actively running. Screenshots and documentation in this repository preserve the results of the completed implementation and testing.

## Future Improvements

If the lab were expanded in the future, potential improvements would include:

- Create additional Elastic Security detection rules for different attack techniques.
- Integrate Suricata alerts more extensively with Elastic Security.
- Develop detection and investigation scenarios for network reconnaissance such as Nmap scanning.
- Add Windows security monitoring and Windows-specific detection scenarios.
- Simulate additional attacks from Kali Linux to test detection coverage.
- Create dashboards for visualising authentication failures, network activity, and security alerts.
- Map additional detection rules to the MITRE ATT&CK framework.
- Implement alert severity levels and improved investigation workflows.
- Expand the environment with additional endpoints and services to better represent an enterprise network.

## Project Outcome

This project provided practical experience building and operating a small Security Operations Centre environment using the Elastic Stack.

The lab demonstrated the process of generating attack activity, collecting security telemetry, analysing events in Kibana, and creating a detection rule capable of identifying simulated SSH brute-force activity.

Although the environment was built for educational purposes, the project provided hands-on experience with concepts used in real SOC environments, including:

- SIEM administration
- Centralised log collection
- Endpoint monitoring
- Network monitoring
- Security event investigation
- Detection engineering
- Attack simulation
- MITRE ATT&CK mapping

The project and supporting evidence have been preserved in this repository as documentation of the implementation and testing process.