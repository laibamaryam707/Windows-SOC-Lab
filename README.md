# Windows SOC Monitoring Lab

## Overview

This project demonstrates the deployment of a Windows Security Operations Center (SOC) monitoring lab using Splunk Enterprise, Sysmon, Splunk Universal Forwarder, and VMware Workstation.

The lab provides centralized Windows endpoint monitoring through Sysmon telemetry, enabling log analysis, alert triage, threat hunting, and security investigations. A custom Splunk dashboard was developed to visualize security events and support incident analysis.

---

## Objectives

- Build a Windows endpoint monitoring lab
- Collect and centralize Sysmon logs in Splunk
- Develop a real-time security monitoring dashboard
- Create SPL queries for endpoint visibility
- Perform security investigations and basic threat hunting

---

## Lab Architecture

```
Windows 11 Virtual Machine
          │
          ▼
       Sysmon
          │
          ▼
Splunk Universal Forwarder
          │
          ▼
   Splunk Enterprise
          │
          ▼
Windows SOC Monitoring Dashboard
```

---

## Technology Stack

- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- VMware Workstation
- Windows 11
- PowerShell
- SPL (Search Processing Language)

---

## Dashboard Features

- Total Security Events
- Process Creation Monitoring
- File Creation Monitoring
- PowerShell Activity
- Command Prompt Activity
- Active Hosts
- Top Users
- Event Timeline
- Top Processes
- High-Risk Processes
- Event Severity Distribution
- MITRE ATT&CK Technique Mapping
- Recent Sysmon Events

---

## Dashboard Preview

![Windows SOC Dashboard](Screenshots/SOC_Monitoring.jpeg)

---

## Repository Structure

```
Windows-SOC-Lab
│
├── Dashboard
├── Investigations
├── Lab Setup
├── Screenshots
├── SPL Queries
└── README.md
```

---

## Skills Demonstrated

- SIEM Monitoring
- Splunk Dashboard Development
- SPL Query Development
- Windows Event Analysis
- Sysmon Monitoring
- Log Analysis
- Alert Triage
- Threat Hunting
- Incident Investigation
- IOC Analysis
- Digital Forensics Fundamentals

---

## Future Enhancements

The following investigations are planned to expand the lab:

- Encoded PowerShell Detection
- Scheduled Task Persistence
- Registry Persistence
- Network Connection Analysis (Sysmon Event ID 3)
- IOC Correlation
- Advanced Threat Hunting
- Additional MITRE ATT&CK Detection Rules

---

## Author

**Laiba Maryam**

Cybersecurity | SOC Analyst | Digital Forensics | Threat Hunting
