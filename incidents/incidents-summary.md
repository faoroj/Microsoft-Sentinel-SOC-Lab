# Incident Report

## Incident Name
Suspicious Authentication Activity

## Summary
Microsoft Sentinel generated an alert after detecting multiple failed login attempts followed by a successful login from a different geographic location.

## Investigation Steps
- Reviewed sign-in logs
- Identified source IP addresses
- Checked geolocation
- Analyzed user behavior timeline

## Findings
- 12 failed login attempts from IP X.X.X.X
- Successful login from a different country within a short timeframe
- Activity consistent with credential attack

## Response Actions
- Recommended password reset
- Enabled MFA
- Blocked a malicious IP

## MITRE ATT&CK
T1110 – Brute Force  
T1078 – Valid Accounts
