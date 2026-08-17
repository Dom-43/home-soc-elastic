# Suricata IDS

## Overview

Suricata was installed on the Ubuntu Server to provide network-based intrusion detection capabilities within the Home SOC Lab.

While Elastic Agent collects and forwards host-based logs, Suricata monitors network traffic and can identify suspicious network activity.

This adds an additional source of security telemetry to the SOC environment.

## Architecture

The lab uses the following structure:

Kali Linux  
↓  
Network Traffic  
↓  
Ubuntu Server  
↓  
Suricata IDS  
↓  
Security Events / Logs  
↓  
Elastic Stack

## Purpose

Suricata was included in the lab to demonstrate how a SOC can combine host-based and network-based monitoring.

The environment can therefore observe activity from multiple perspectives:

- Linux authentication events
- SSH activity
- Network connections
- Network scanning activity
- Suricata IDS events

## Testing

Kali Linux was used to generate network activity against the Ubuntu Server.

Nmap was used during testing to scan the server and generate traffic that could be observed by the monitoring environment.

Example:

```bash
nmap <UBUNTU-SERVER-IP>
