# Incident Report: Repeated Failed SMB Authentication

## Incident ID

```text
INC-001
```

---

## Incident Title

Repeated Failed SMB Authentication Attempts

---

## Detection Source

```text
Splunk Enterprise
Windows Security Event Log
```

---

## SIEM Host

```text
Operating System: Ubuntu Linux
Platform: Splunk Enterprise
```

---

## Severity

```text
Low
```

---

# Summary

Five failed SMB authentication attempts were detected against a Windows 11 lab endpoint.

The authentication attempts targeted the local Windows account `socuser` and originated from the Kali Linux VM inside the controlled Home SOC Lab.

Windows recorded the failed authentication activity as Security Event ID 4625.

The Splunk Universal Forwarder sent the Windows Security events to Splunk Enterprise running on the Ubuntu laptop.

An SPL threshold-based detection successfully identified the repeated authentication failures.

---

# Affected Asset

```text
Hostname: SOC-Windows
Operating System: Windows 11
```

---

# Source System

```text
Source IP: 192.168.50.10
Operating System: Kali Linux
Role: Authorized security testing VM
```

---

# Target Account

```text
Account Name: socuser
```

---

# Event Information

```text
Event ID: 4625
Log Source: WinEventLog:Security
Failed Attempts: 5
Protocol: SMB
```

---

# Initial Search

```spl
index=main host="SOC-Windows"
source="WinEventLog:Security"
EventCode=4625
earliest=-30m
```

---

# Detection Query

```spl
index=main host="SOC-Windows"
source="WinEventLog:Security"
EventCode=4625
earliest=-30m
| stats count by Account_Name, Source_Network_Address
| where count >= 5
```

---

# Investigation

The Windows Security logs were reviewed using Splunk Enterprise.

The investigation identified repeated failed authentication events associated with:

```text
Account: socuser
Source IP: 192.168.50.10
Count: 5
```

The source IP was confirmed to belong to the Kali Linux VM used for authorized security testing.

The Windows endpoint forwarded the authentication events through the Splunk Universal Forwarder to Splunk Enterprise running on Ubuntu Linux.

No successful authentication was observed during the controlled test.

---

# Findings

The activity represented repeated failed SMB authentication attempts from a single source system against one Windows account.

The SPL query successfully grouped the failed authentication events by account name and source IP address.

The threshold condition identified the activity when the event count reached five.

---

# Indicators

```text
Source IP: 192.168.50.10
Target Account: socuser
Destination Host: SOC-Windows
Event ID: 4625
Protocol: SMB
```

---

# Response Actions

- Reviewed Windows Security Event ID 4625 events
- Identified the targeted account
- Identified the source IP address
- Verified the number of failed attempts
- Confirmed the source IP belonged to the Kali Linux VM
- Checked for successful authentication
- Confirmed the activity was authorized lab testing
- Tested threshold-based SPL detection logic
- Documented the investigation

---

# Root Cause

The activity was intentionally generated from the Kali Linux VM as part of authorized security detection testing inside the Home SOC Lab.

---

# Resolution

The authentication activity was confirmed as expected lab traffic.

No compromise occurred.

The detection was considered successful because Splunk identified the repeated failed authentication attempts and associated them with the correct account and source IP address.

---

# Lessons Learned

This exercise demonstrated that:

- Windows Security Event ID 4625 records failed authentication activity
- The Splunk Universal Forwarder can send Windows security telemetry to a separate SIEM system
- Splunk Enterprise can be hosted centrally on Ubuntu Linux
- Source IP addresses are useful during authentication investigations
- Account names can be correlated with authentication activity
- SPL `stats` can aggregate related security events
- Threshold logic can identify repeated authentication failures
- Controlled attack simulation can validate defensive detections

---

# Status

```text
Closed
```
