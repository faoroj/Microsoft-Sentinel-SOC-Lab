# Brute Force Detection – KQL

## Objective
Detect multiple failed login attempts against a single user.

## Query

SigninLogs
| where ResultType != 0
| summarize FailedAttempts = count() by UserPrincipalName, IPAddress
| where FailedAttempts > 5

## Detection Logic
Identifies potential brute-force attempts targeting user accounts.

## MITRE ATT&CK
T1110 – Brute Force
