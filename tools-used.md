# Tools Used

## Overview

This document describes the technologies currently used in the Home SOC Lab and how each one contributes to the security monitoring and detection workflow.

Only tools that have actually been used in the lab are listed as current tools.

---

# Ubuntu Linux

Ubuntu Linux runs on the physical laptop hosting Splunk Enterprise.

The Ubuntu laptop acts as the central SIEM host.

Current responsibilities include:

- Hosting Splunk Enterprise
- Receiving forwarded Windows logs
- Receiving Sysmon telemetry
- Running Splunk searches
- Supporting detection development
- Supporting incident investigations

---

# Oracle VirtualBox

Oracle VirtualBox hosts the virtual machines used in the SOC lab.

Current virtual machines:

- Windows 11
- Kali Linux

VirtualBox provides the controlled environment used for security testing and monitoring.

---

# Windows 11

Windows 11 is the primary monitored endpoint.

Hostname:

```text
SOC-Windows
```

The system provides:

- Windows Security Event Logs
- Authentication activity
- Sysmon telemetry
- PowerShell administration
- Splunk Universal Forwarder support

---

# Kali Linux

Kali Linux is used as the authorized security testing system.

Current uses include:

- Nmap scanning
- SMB testing
- Service discovery
- Controlled failed authentication attempts
- Generating activity for detection practice

All testing is conducted only against systems inside the controlled lab environment.

---

# Splunk Enterprise

Splunk Enterprise runs on the Ubuntu laptop and serves as the central SIEM platform.

It is used to:

- Receive forwarded Windows logs
- Search Windows Security events
- Analyze Sysmon telemetry
- Investigate authentication failures
- Write SPL queries
- Create threshold-based detections
- Correlate accounts and source IP addresses

---

# Splunk Universal Forwarder

The Splunk Universal Forwarder is installed on the Windows endpoint.

Its purpose is to forward Windows telemetry to Splunk Enterprise running on the Ubuntu laptop.

Current forwarded data includes:

```text
WinEventLog:Security
```

and:

```text
WinEventLog:Microsoft-Windows-Sysmon/Operational
```

---

# Sysmon

Sysmon provides enhanced Windows endpoint telemetry.

The lab currently uses Sysmon Event ID 3 for network connection monitoring.

Example Splunk search:

```spl
index=main host="SOC-Windows"
source="WinEventLog:Microsoft-Windows-Sysmon/Operational"
"<EventID>3</EventID>"
```

---

# Windows Security Event Log

The Windows Security Event Log provides authentication telemetry used during SOC investigations.

A primary event used in this lab is:

```text
Event ID 4625
```

Event ID 4625 indicates that an account failed to log on.

Example Splunk search:

```spl
index=main host="SOC-Windows"
source="WinEventLog:Security"
EventCode=4625
earliest=-30m
```

---

# PowerShell

PowerShell is used on the Windows endpoint for administration and configuration.

It has been used to:

- Create lab test accounts
- Verify system configuration
- Run networking commands
- Configure and troubleshoot the endpoint

---

# Nmap

Nmap is used from Kali Linux for authorized network and service discovery.

Example:

```bash
nmap -p 445 -sV 192.168.50.20
```

This command was used to confirm that SMB was reachable on the Windows endpoint.

---

# smbclient

`smbclient` was used from Kali Linux to generate controlled failed SMB authentication attempts against the Windows endpoint.

These failed attempts generated Windows Security Event ID 4625 events that were forwarded to Splunk for investigation.

---

# Splunk Search Processing Language (SPL)

SPL is used to search, aggregate, analyze, and detect activity stored in Splunk.

Example detection:

```spl
index=main host="SOC-Windows"
source="WinEventLog:Security"
EventCode=4625
earliest=-30m
| stats count by Account_Name, Source_Network_Address
| where count >= 5
```

This query identifies repeated authentication failures by account and source IP address.

---

# Skills Practiced

Tools in this lab have been used to practice:

- SIEM monitoring
- Windows log analysis
- Endpoint monitoring
- Authentication monitoring
- Threat detection
- Splunk SPL
- Network service discovery
- Source IP correlation
- Security event aggregation
- Incident investigation
- Technical documentation# Tools Used

## Overview

This document describes the tools currently used in the Home SOC Lab and the purpose of each one.

Only tools that have been actively used in the lab are listed as current tools.

---

## Ubuntu Linux

Ubuntu Linux is installed on the physical laptop that hosts Splunk Enterprise.

The Ubuntu system acts as the central SIEM host for the lab.

Current responsibilities include:

- Hosting Splunk Enterprise
- Receiving forwarded Windows logs
- Receiving Sysmon telemetry
- Running Splunk searches
- Supporting detection and investigation workflows

---

## Oracle VirtualBox

Oracle VirtualBox is used to host the lab virtual machines.

Current virtual machines include:

- Windows 11
- Kali Linux

VirtualBox provides the isolated environment used for security testing and monitoring.

---

## Windows 11

Windows 11 is used as the primary monitored endpoint.

Hostname:

```text
SOC-Windows
