# Cybersecurity Home Lab

## Overview
This repo documents my personal cybersecurity home lab used to develop hands-on skills in networking, detection, SecOps, and attack simulation.
The lab is designed to mirror a small enterprise-style environment with clear separation between attacker, victim, and monitoring systems.

## Repo Map
- `architecture/` — lab overview and network diagram
- `setup/` — build notes and configuration steps
- `attacks/` — attack simulations and MITRE mappings
- `detection/` — Splunk content and detections
- `pcaps/` — packet captures (sanitised)
- `notes/` — lessons learned / troubleshooting log

- ## Project Status
Active : building out victim configuration and initial detections in Splunk.

## Objectives
- Practice real-world SecOps workflows
- Simulate common attack techniques in a controlled environment
- Analyse network traffic and host logs
- Build detection logic aligned to certs such as Security+ and CySA+

## Lab Environment
- **Main Laptop (Host / Monitoring)**
  - Windows 11
  - Network management and analysis
  - Splunk for log ingestion and detection

- **Attacker Laptop**
  - Kali Linux (VM)
  - Used for reconnaissance and attack simulation

- **Victim Laptop**
  - Dedicated victim system (in progress)
  - Will be used to generate realistic attack telemetry

- **Networking**
  - Isolated internal lab network
  - Private RFC1918 addressing (`10.10.10.0/24`)
  - Managed switch and dedicated Ethernet interfaces

## What This Demonstrates
- Network segmentation and isolation
- Blue team / SOC mindset
- Attack simulation and detection
- Log analysis and PCAP investigation
- Structured technical documentation

## Current Focus
- Lab network stabilisation
- Splunk ingestion and baseline detections
- Initial attack simulations from Kali Linux

## Disclaimer
All activity is conducted within an isolated lab environment.
No testing is performed against production or external systems.
