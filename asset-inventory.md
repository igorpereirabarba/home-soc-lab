# Asset Inventory

## Overview

This document lists the systems and tools currently used in the Home SOC Lab.

The environment is intentionally small and isolated so that security events can be generated, collected, analyzed, and documented safely.

---

## Virtual Machines

| Asset | Operating System | Purpose |
|---|---|---|
| SOC-Windows | Windows 11 | Endpoint, Windows Security log source, and Sysmon telemetry source |
| Kali Linux VM | Kali Linux | Authorized testing, reconnaissance, and activity generation |

---

## Security Monitoring Components

| Component | Purpose |
|---|---|
| Splunk Enterprise | SIEM platform used to search, analyze, and detect security events |
| Splunk Universal Forwarder | Sends Windows event logs and Sysmon data to Splunk |
| Sysmon | Provides detailed Windows endpoint telemetry |
| Windows Security Event Log | Records authentication and security-related events |

---

## Virtualization Platform

| Platform | Purpose |
|---|---|
| Oracle VirtualBox | Hosts and connects the virtual machines used in the lab |

---

## Current Network Roles

### SOC-Windows

Primary functions:

- Windows endpoint
- Security event generation
- Windows Security Event Log source
- Sysmon telemetry source
- Splunk Universal Forwarder host

### Kali Linux VM

Primary functions:

- Authorized testing
- Nmap scanning
- SMB authentication testing
- Generating activity for detection practice

---

## Current Lab Scope

The current lab contains:

- One Windows endpoint
- One Kali Linux testing system
- One Splunk Enterprise instance
- Windows Security Event collection
- Sysmon telemetry collection
- Authentication failure detection

---

## Future Expansion

Possible future assets may include:

- Ubuntu Server VM
- Additional Windows endpoints
- Additional Linux endpoints
- Wireshark packet captures
- Additional SIEM integrations
- Active Directory lab systems
- Firewall or IDS telemetry
