# Tools Used

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
