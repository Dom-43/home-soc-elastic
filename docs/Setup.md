# Home SOC Lab Setup

## Overview

This project demonstrates the creation of a Home Security Operations Centre (SOC) using the Elastic Stack. The lab was built in a virtual environment using UTM on macOS and simulates common attack scenarios to generate and analyse security events.

The objective was to gain hands-on experience with log collection, endpoint monitoring, intrusion detection, and alert investigation using industry-standard security tools.

---

## Lab Architecture

| Component | Purpose |
|-----------|---------|
| Ubuntu Server | Central SOC server hosting Elastic Stack and Suricata |
| Kali Linux | Attack machine used to simulate security events |
| Elasticsearch | Stores and indexes security logs |
| Kibana | Security monitoring and investigation interface |
| Fleet Server | Centralised management of Elastic Agents |
| Elastic Agent | Collects endpoint telemetry and forwards logs |
| Suricata IDS | Network intrusion detection |

---

## Environment

### Host Machine

- macOS
- UTM Virtual Machine Manager

### Virtual Machines

#### Ubuntu Server

Responsibilities:

- Elasticsearch
- Kibana
- Fleet Server
- Elastic Agent
- Suricata IDS

#### Kali Linux

Tools used:

- Hydra
- Nmap
- SSH

Purpose:

- Generate attack traffic
- Validate detections

---

## Elastic Stack

The Elastic Stack was deployed on the Ubuntu Server.

Installed components:

- Elasticsearch
- Kibana
- Fleet Server
- Elastic Agent

Elastic Agents were enrolled through Fleet to centralise log collection and monitoring.

---

## Suricata

Suricata was installed on the Ubuntu Server to inspect network traffic and generate IDS alerts.

Generated alerts were forwarded into Elasticsearch through Elastic Agent where they became searchable in Kibana.

---

## Validation

The lab was validated by generating realistic security events.

Completed attack simulations include:

- SSH brute-force attack using Hydra
- Network reconnaissance using Nmap SYN Scan

Both attacks successfully generated logs and alerts that were visible within Kibana.

---

## Project Outcome

The completed lab demonstrates:

- Elastic Stack deployment
- Fleet Server management
- Endpoint log collection
- Network intrusion detection
- Alert generation
- Security event investigation