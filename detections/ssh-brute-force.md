# SSH Brute Force Detection

## Overview

This detection rule was created in Elastic Security to identify repeated failed SSH authentication attempts against the Ubuntu server.

The attack was simulated from the Kali Linux machine using Hydra. Authentication logs from the Ubuntu server were collected by Elastic Agent and sent to Elasticsearch for analysis.

## Attack Scenario

The Kali Linux machine was used as the attacking system.

Hydra generated multiple SSH authentication attempts against the Ubuntu server:

Kali Linux  
↓  
Hydra SSH Attack  
↓  
Ubuntu SSH Server  
↓  
Failed Authentication Logs  
↓  
Elastic Agent  
↓  
Elasticsearch  
↓  
Elastic Security Detection Rule  
↓  
Security Alert

## Detection Logic

The detection looks for repeated SSH authentication failures within a short period of time.

These events indicate that a remote system may be attempting to guess valid SSH credentials.

## Data Source

The detection uses Linux authentication logs collected from the Ubuntu server by Elastic Agent.

Relevant information includes:

- Failed SSH authentication events
- Source IP address
- Username used during the authentication attempt
- Timestamp of each attempt
- Host receiving the connection

## Detection Result

During testing, Hydra generated multiple failed SSH authentication attempts.

Elastic successfully ingested the authentication events and the detection rule generated a security alert.

This demonstrated that the SOC environment could detect simulated SSH brute-force activity.

## MITRE ATT&CK Mapping

**Tactic:** Credential Access

**Technique:** Brute Force

**MITRE ATT&CK ID:** T1110

## Investigation

When an alert is generated, a SOC analyst could investigate:

- Source IP address
- Number of authentication failures
- Targeted usernames
- Target host
- Time between login attempts
- Whether a successful login occurred after the failures

A successful authentication following numerous failures could indicate that an account was compromised.