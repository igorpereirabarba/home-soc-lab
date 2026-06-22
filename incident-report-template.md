# Incident Report Template

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
