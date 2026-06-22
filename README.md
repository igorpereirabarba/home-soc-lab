# Home SOC Lab

## Project Overview

This project documents the creation of a beginner home Security Operations Center (SOC) lab designed to practice security monitoring, log analysis, alert investigation, and incident response.

The goal of this lab is to build hands-on experience with tools and concepts used by SOC analysts, including SIEM monitoring, Windows Event Logs, Linux logs, endpoint activity, network scanning, and technical documentation.

## Career Goal

This lab was created as part of my path toward becoming a SOC Analyst / Cybersecurity Analyst. The project focuses on building practical skills in:

* Security monitoring
* Log analysis
* Incident response
* SIEM alert investigation
* Endpoint security
* Network traffic analysis
* Threat detection
* Technical documentation

## Lab Environment

The lab will use virtual machines to simulate a small enterprise environment.

| System           | Purpose                                  |
| ---------------- | ---------------------------------------- |
| Windows 10/11 VM | Workstation and endpoint log source      |
| Ubuntu Server VM | Linux server and log source              |
| Kali Linux VM    | Testing and scanning machine             |
| Wazuh SIEM       | Log collection, monitoring, and alerting |

## Tools Planned

* VirtualBox
* Windows Event Viewer
* Wazuh SIEM
* Sysmon
* Ubuntu Server
* Kali Linux
* Nmap
* Wireshark
* PowerShell
* Linux command line

## Planned Network Diagram

```text
Host Laptop
│
├── Windows VM
│   └── Sends Windows logs to Wazuh
│
├── Ubuntu Server VM
│   └── Sends Linux logs to Wazuh
│
├── Kali Linux VM
│   └── Simulates scanning and testing activity
│
└── Wazuh Server
    └── Collects and displays security alerts
```

## Project Phases

### Phase 0: Documentation

Before installing tools, this phase focuses on creating the project structure, documenting the lab purpose, identifying planned assets, and defining learning goals.

### Phase 1: Windows Logging

This phase will focus on Windows Event Viewer, failed login attempts, successful logins, system logs, application logs, and basic endpoint investigation.

### Phase 2: SIEM Setup

This phase will focus on installing Wazuh, connecting endpoint agents, collecting logs, and reviewing security alerts.

### Phase 3: Network Scanning Detection

This phase will use Kali Linux and Nmap to simulate basic reconnaissance activity inside the lab environment.

### Phase 4: Incident Response Documentation

This phase will focus on writing SOC-style investigation notes and incident reports based on alerts generated in the lab.

## Planned SOC Investigations

### 1. Failed Login Detection

Objective: Detect failed login attempts on a Windows endpoint.

Skills practiced:

* Windows Event Viewer
* Security logs
* Failed authentication investigation
* SOC-style documentation

### 2. Nmap Scan Detection

Objective: Use Kali Linux to scan a lab machine and identify suspicious network activity.

Skills practiced:

* Nmap
* Port scanning
* Network reconnaissance
* Alert review
* Incident analysis

### 3. Suspicious PowerShell Activity

Objective: Generate and investigate suspicious PowerShell activity on a Windows endpoint.

Skills practiced:

* PowerShell logging
* Windows security monitoring
* Endpoint investigation
* Detection documentation

## What I Am Learning

Through this lab, I am learning how SOC analysts collect logs, review alerts, investigate suspicious activity, document findings, and recommend response actions.

This project strengthens my understanding of:

* Windows security events
* Linux system activity
* SIEM dashboards
* Alert investigation
* Network reconnaissance
* Incident response workflow
* Cybersecurity documentation

## Future Improvements

Planned improvements include:

* Add Sysmon advanced logging
* Add MITRE ATT&CK mapping
* Add phishing email analysis
* Add vulnerability scanning with Nessus Essentials or OpenVAS
* Add Splunk or Microsoft Sentinel practice
* Create more incident reports
* Add screenshots for every phase
