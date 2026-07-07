# Windows SOC Monitoring Lab - Lab Setup

## Overview

This project demonstrates the deployment of a Windows Security Operations Center (SOC) monitoring lab using Splunk Enterprise, Sysmon, and Splunk Universal Forwarder. The lab was built in VMware Workstation to simulate endpoint monitoring, security investigations, and threat hunting.

---

# Lab Architecture

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
Windows Security Health Monitoring Dashboard
```

---

# Environment

| Component | Description |
|-----------|-------------|
| Hypervisor | VMware Workstation |
| Operating System | Windows 11 |
| SIEM Platform | Splunk Enterprise |
| Endpoint Agent | Splunk Universal Forwarder |
| Endpoint Monitoring | Sysmon |
| Log Source | Windows Event Logs & Sysmon Operational Logs |

---

# Configuration

## 1. Windows Virtual Machine

- Installed Windows 11 in VMware Workstation.
- Configured networking for communication between the endpoint and Splunk.
- Installed Windows updates and required dependencies.

---

## 2. Sysmon Installation

- Installed Microsoft Sysmon.
- Enabled process creation monitoring.
- Enabled file creation monitoring.
- Enabled registry event logging.
- Enabled network connection monitoring.
- Generated detailed Windows endpoint telemetry.

---

## 3. Splunk Enterprise

- Installed Splunk Enterprise.
- Created a dedicated **sysmon** index.
- Configured data indexing and search capabilities.
- Verified successful ingestion of Sysmon events.

---

## 4. Splunk Universal Forwarder

Configured the Universal Forwarder to collect:

- Microsoft-Windows-Sysmon/Operational
- Security
- Application
- System

Forwarded logs to Splunk Enterprise for centralized monitoring.

---

## Dashboard Development

Built a Windows Security Health Monitoring Dashboard containing:

- Total Security Events
- Process Creation Events
- File Creation Events
- PowerShell Activity
- Command Prompt Activity
- Active Hosts
- Top Users
- Event Timeline
- Top Processes
- High-Risk Processes
- MITRE ATT&CK Technique Mapping
- Event Severity Distribution
- Recent Sysmon Events

---

## Skills Demonstrated

- Splunk Enterprise Administration
- Sysmon Configuration
- Windows Event Collection
- SIEM Dashboard Development
- SPL Query Development
- Log Analysis
- Security Monitoring
- Alert Triage
- Threat Hunting
- Incident Investigation
