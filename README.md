# Microsoft Sentinel SOC Lab

## Overview
This project simulates a real-world Security Operations Center (SOC) workflow using Microsoft Sentinel. The lab focuses on detecting, investigating, and responding to suspicious authentication activity using Entra ID sign-in logs and custom detection logic.

The objective is to demonstrate hands-on experience with SIEM configuration, log analysis, threat detection, and incident response in a cloud-based security environment.

---

## Objectives
- Deploy and configure Microsoft Sentinel
- Connect and ingest Entra ID sign-in logs
- Simulate suspicious authentication activity
- Develop custom detection rules using KQL
- Investigate security incidents within Sentinel
- Document findings using SOC-style reporting
- Map activity to MITRE ATT&CK techniques

---

## Environment

| Component | Technology |
|---|---|
| SIEM | Microsoft Sentinel |
| Log Storage | Azure Log Analytics Workspace |
| Identity Source | Microsoft Entra ID |
| Cloud Platform | Microsoft Azure |
| Query Language | Kusto Query Language (KQL) |

---

## Architecture

1. Created an Azure Log Analytics Workspace  
2. Deployed Microsoft Sentinel  
3. Connected Entra ID data connector to ingest sign-in logs  
4. Generated simulated authentication activity  
5. Created detection rules using KQL  
6. Investigated triggered incidents in Sentinel  

Architecture diagram available in: /architecture/


---

## Attack Simulation Scenarios

The following behaviors were generated to simulate potential malicious activity:

- Multiple failed login attempts (brute-force simulation)
- Successful login following repeated failures
- Authentication attempts from different geographic locations
- Suspicious IP address activity

Simulation steps documented in: /attack-simulation/


---

## Detection Engineering

Custom detection logic was created using KQL to identify suspicious patterns.

### Example: Brute Force Detection

```kql
SigninLogs
| where ResultType != 0
| summarize FailedAttempts = count() by UserPrincipalName, IPAddress
| where FailedAttempts > 5

```

architecture/        → Environment design and diagrams  
data-sources/        → Log ingestion configuration  
attack-simulation/   → Steps used to generate test activity  
detections/          → KQL queries and detection logic  
incidents/           → Investigation reports and findings  
evidence/            → Screenshots and supporting artifacts  
