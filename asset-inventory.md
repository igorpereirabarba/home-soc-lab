# Asset Inventory

## Overview

This document lists the systems and security components currently used in the Home SOC Lab.

The environment is designed to simulate a small Security Operations Center workflow where activity can be generated, logged, forwarded, analyzed, and documented.

---

## Systems

| Asset | Operating System | Purpose |
|---|---|---|
| Ubuntu Laptop | Ubuntu Linux | Hosts Splunk Enterprise and serves as the central SIEM system |
| SOC-Windows | Windows 11 VM | Monitored endpoint, Windows Security log source, and Sysmon telemetry source |
| Kali Linux VM | Kali Linux | Authorized testing, scanning, and security activity generation |

---

## Security Monitoring Components

| Component | Location | Purpose |
|---|---|---|
| Splunk Enterprise | Ubuntu Laptop | Central SIEM platform used for log search, investigation, and detection |
| Splunk Universal Forwarder | SOC-Windows | Forwards Windows logs and Sysmon telemetry to Splunk |
| Sysmon | SOC-Windows | Provides detailed Windows endpoint telemetry |
| Windows Security Event Log | SOC-Windows | Records authentication and other security-related activity |

---

## Virtualization Platform

| Platform | Purpose |
|---|---|
| Oracle VirtualBox | Hosts the Windows 11 and Kali Linux virtual machines |

---

## Current System Roles

### Ubuntu Laptop

Primary functions:

- Hosts Splunk Enterprise
- Receives logs from the Windows endpoint
- Stores and searches Windows Security events
- Stores and searches Sysmon telemetry
- Runs SPL queries
- Supports detection and investigation workflows

### SOC-Windows

Primary functions:

- Windows endpoint
- Windows Security Event Log source
- Sysmon telemetry source
- Splunk Universal Forwarder host
- Target system for authorized lab testing

### Kali Linux VM

Primary functions:

- Authorized testing
- Network reconnaissance
- Nmap scanning
- SMB authentication testing
- Generating security telemetry for detection practice

---

## Current Lab Scope

The current lab includes:

- One Ubuntu SIEM host
- One Windows 11 endpoint
- One Kali Linux testing system
- Windows Security Event collection
- Sysmon telemetry collection
- Splunk log ingestion
- Authentication failure detection
- Network connection monitoring

---

## Current Detection Use Cases

The lab currently supports:

- Sysmon network connection analysis
- Windows failed logon investigation
- Repeated authentication failure detection
- Source IP correlation
- Account-based event aggregation

---

## Future Expansion

Possible future additions include:

- Wireshark packet analysis
- Splunk dashboards
- Additional Windows endpoints
- Additional Linux endpoints
- Active Directory
- Windows Defender Firewall logging
- IDS/IPS telemetry
- RDP authentication monitoring
- Additional incident reports
- MITRE ATT&CK mappings
