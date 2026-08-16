# Incident Report Template

## Incident ID

```text
INC-XXX
```

---

## Incident Title

Enter a concise title describing the detected activity.

Example:

```text
Repeated Failed Authentication Attempts
```

---

## Date and Time

```text
YYYY-MM-DD HH:MM
```

---

## Detection Source

```text
Splunk Enterprise
Windows Security Event Log
```

---

## Severity

Select one:

- Low
- Medium
- High
- Critical

---

# Summary

Provide a concise description of what was detected.

Include:

- What happened
- What system was affected
- Where the activity originated
- What detection identified the activity

---

# Affected Asset

```text
Hostname:
IP Address:
Operating System:
```

---

# SIEM Host

```text
Operating System: Ubuntu Linux
Platform: Splunk Enterprise
```

---

# Source System

```text
Source IP:
Hostname:
Operating System:
```

---

# Target Account

```text
Account Name:
```

---

# Event Information

```text
Event ID:
Log Source:
Event Count:
Protocol:
```

---

# Detection Query

```spl
Insert SPL query here
```

---

# Investigation

Document the investigation process.

Questions to answer:

- What account was targeted?
- What source IP generated the activity?
- How many events occurred?
- Over what period did the events occur?
- Was authentication successful?
- Were other accounts targeted?
- Were related events present?
- Was the activity expected or suspicious?

---

# Findings

Summarize what was discovered during the investigation.

Example:

The investigation identified five failed authentication attempts against one account from a single source IP address. No successful authentication was observed.

---

# Indicators

```text
Source IP:
Username:
Event ID:
Destination Host:
Protocol:
```

---

# Response Actions

Document actions taken during the investigation.

Possible actions include:

- Reviewed authentication events
- Identified source IP
- Identified targeted account
- Checked for successful authentication
- Reviewed related events
- Confirmed whether activity was authorized
- Tested detection logic
- Documented findings

---

# Root Cause

Describe the reason the activity occurred.

---

# Resolution

Describe how the incident was resolved or closed.

---

# Lessons Learned

Document lessons learned from the investigation.

Possible examples:

- Which Windows event identified the activity
- Which fields were useful during investigation
- Which SPL commands were useful
- How detection logic could be improved

---

# MITRE ATT&CK Mapping

```text
Tactic:
Technique:
Technique ID:
```

Complete this section when applicable.

---

# Status

Select one:

```text
Open
Investigating
Resolved
Closed
```# Incident Report Template

## Incident Title

Example: Multiple Failed Login Attempts Detected

## Date and Time

Date:  
Time:  

## Analyst

Igor Barbosa

## Alert Source

Example: Windows Event Viewer / Wazuh SIEM

## Systems Involved

| Hostname | IP Address | Operating System | Role |
|---|---|---|---|
| TBD | TBD | TBD | TBD |

## Summary

Briefly describe what happened.

Example:

Multiple failed login attempts were observed on a Windows endpoint. The activity may indicate a user mistyping a password, a misconfigured service, or a possible brute-force attempt.

## Evidence Collected

Include screenshots, log entries, event IDs, timestamps, usernames, IP addresses, and affected systems.

Evidence examples:

- Screenshot of alert
- Windows Event ID
- Source IP address
- Username involved
- Time of event
- SIEM alert details

## Analysis

Explain why the activity is suspicious and what it may indicate.

Questions to answer:

- What happened?
- Which system was affected?
- Which user account was involved?
- Was the activity expected or unusual?
- Could this indicate malicious activity?
- Does the event require escalation?

## Possible Cause

Examples:

- User forgot password
- Brute-force attempt
- Misconfigured service
- Unauthorized access attempt
- Scheduled task or application error

## Severity

Low / Medium / High / Critical

## Recommended Response

Examples:

- Verify whether the user attempted the login
- Check source IP address
- Review recent successful logins
- Reset password if needed
- Lock account if activity appears malicious
- Escalate to security team if suspicious activity continues

## Lessons Learned

Write what you learned from the investigation.

Example:

This investigation helped me understand how failed login attempts appear in Windows logs and how SOC analysts review authentication activity to identify suspicious behavior.
