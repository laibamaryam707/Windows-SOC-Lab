# Windows SOC Monitoring Lab – SPL Queries

This document contains the SPL (Search Processing Language) queries used to build the Windows Security Health Monitoring dashboard. These searches provide visibility into endpoint activity, process execution, user behavior, and potential security threats collected through Sysmon and Splunk Enterprise.

---

# 1. Total Security Events

**Purpose:** Displays the total number of Sysmon events collected.

```spl
index=sysmon
| stats count
```

---

# 2. Process Creation Events

**Purpose:** Counts all process creation events (Sysmon Event ID 1).

```spl
index=sysmon EventCode=1
| stats count
```

---

# 3. File Creation Events

**Purpose:** Counts all file creation events (Sysmon Event ID 11).

```spl
index=sysmon EventCode=11
| stats count
```

---

# 4. PowerShell Activity

**Purpose:** Detects PowerShell process execution.

```spl
index=sysmon EventCode=1 Image="*powershell*"
| stats count
```

---

# 5. Command Prompt Activity

**Purpose:** Detects Command Prompt execution.

```spl
index=sysmon EventCode=1 Image="*cmd.exe"
| stats count
```

---

# 6. Event Timeline

**Purpose:** Displays the volume of Sysmon events over time.

```spl
index=sysmon
| timechart span=15m count
```

---

# 7. Event Distribution by Event ID

**Purpose:** Shows the frequency of each Sysmon Event ID.

```spl
index=sysmon
| stats count by EventCode
```

---

# 8. Top Executed Processes

**Purpose:** Displays the ten most frequently executed processes.

```spl
index=sysmon EventCode=1
| top Image limit=10
```

---

# 9. Top Users

**Purpose:** Identifies the users responsible for the highest number of process creation events.

```spl
index=sysmon EventCode=1
| top User
```

---

# 10. Active Hosts

**Purpose:** Displays monitored Windows hosts generating Sysmon events.

```spl
index=sysmon
| top Computer
```

---

# 11. Recent Sysmon Events

**Purpose:** Displays the latest security events collected by Sysmon.

```spl
index=sysmon
| table _time EventCode Image User Computer
| sort -_time
| head 20
```

---

# 12. High-Risk Processes

**Purpose:** Identifies executions of Windows binaries commonly abused by attackers.

```spl
index=sysmon EventCode=1
| search Image="*powershell.exe" OR Image="*cmd.exe" OR Image="*rundll32.exe" OR Image="*regsvr32.exe" OR Image="*mshta.exe" OR Image="*wscript.exe" OR Image="*cscript.exe"
| stats count by Image
| sort -count
```

---

# 13. MITRE ATT&CK Technique Mapping

**Purpose:** Maps selected Sysmon Event IDs to representative MITRE ATT&CK tactics for visualization within the dashboard.

```spl
index=sysmon
| eval Technique=case(
EventCode=1,"Execution",
EventCode=3,"Command and Control",
EventCode=11,"Collection",
EventCode=12 OR EventCode=13 OR EventCode=14,"Persistence",
EventCode=22,"Discovery",
true(),"Other")
| stats count by Technique
```

> **Note:** This mapping is intended for dashboard visualization and learning purposes. It provides representative ATT&CK tactics rather than a complete or official ATT&CK mapping.

---

# 14. Event Severity Distribution

**Purpose:** Categorizes Sysmon events into High, Medium, and Low severity for dashboard visualization.

```spl
index=sysmon
| eval Severity=case(
EventCode IN (1,3),"High",
EventCode IN (11,12,13,14),"Medium",
true(),"Low")
| stats count by Severity
```

> **Note:** Severity levels are custom classifications created for dashboard reporting and do not represent official Microsoft or Splunk severity ratings.

---

## Dashboard Summary

These SPL queries power the **Windows Security Health Monitoring Dashboard**, providing visibility into:

- Windows process creation activity
- PowerShell and Command Prompt execution
- File creation events
- Endpoint activity across monitored hosts
- User activity
- High-risk process execution
- Event severity distribution
- MITRE ATT&CK technique visualization
- Security event trends
- Recent Sysmon events for investigation

The dashboard was built using **Splunk Enterprise**, **Sysmon**, **Splunk Universal Forwarder**, and **VMware Workstation** to support Windows endpoint monitoring, alert triage, threat hunting, and incident investigation.
