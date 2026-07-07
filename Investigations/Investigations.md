# Windows SOC Monitoring Lab - Security Investigations

The following investigations demonstrate how Sysmon telemetry and Splunk were used to analyze Windows endpoint activity and identify potential security threats.

---

# 1. Windows Process Investigation

## Objective

Analyze Windows process creation events to identify unusual or suspicious process execution.

### Data Source

- Sysmon Event ID 1

### Investigation

- Reviewed process execution logs.
- Correlated parent-child process relationships.
- Examined command-line arguments.
- Identified executing users and affected hosts.

### Outcome

Validated process activity and determined whether execution was legitimate or required further investigation.

---

# 2. PowerShell Investigation

## Objective

Identify PowerShell execution that could indicate administrative activity or attacker behavior.

### Data Source

- Sysmon Event ID 1

### Investigation

- Reviewed PowerShell command execution.
- Examined parent processes.
- Identified execution context.
- Analyzed command-line activity.

### Outcome

Distinguished normal administrative activity from suspicious PowerShell execution.

---

# 3. File Creation Investigation

## Objective

Monitor newly created files to identify suspicious file activity.

### Data Source

- Sysmon Event ID 11

### Investigation

- Reviewed file creation events.
- Identified users responsible for file creation.
- Examined affected directories.
- Correlated related process activity.

### Outcome

Validated file creation activity and investigated abnormal behavior.

---

# 4. Threat Hunting

## Objective

Search Windows endpoint telemetry for suspicious activity without relying on alerts.

### Activities

- Reviewed process execution patterns.
- Identified high-risk Windows binaries.
- Examined endpoint activity trends.
- Investigated unusual user behavior.

### Outcome

Improved visibility into Windows endpoint activity and enhanced threat detection.

---

# 5. Phishing Analysis

## Objective

Analyze phishing indicators using email artifacts and OSINT techniques.

### Activities

- Email header analysis.
- URL inspection.
- Attachment review.
- Domain reputation analysis.
- IP address investigation.
- IOC identification.

### Outcome

Identified phishing indicators and documented findings to support incident response.

---

# 6. Digital Forensics

## Objective

Examine Windows artifacts to support security investigations.

### Tool

- Autopsy

### Activities

- File system analysis.
- Windows artifact examination.
- Timeline review.
- Evidence collection.

### Outcome

Recovered forensic artifacts and documented investigation findings.

---

# Planned Investigations

The following investigations are currently being added to expand the Windows SOC Monitoring Lab:

- Encoded PowerShell Detection
- Scheduled Task Persistence
- Registry Run Key Persistence
- Network Connection Monitoring (Sysmon Event ID 3)
- Lateral Movement Detection
- IOC Correlation
- Advanced Threat Hunting
- MITRE ATT&CK Mapping Enhancements

---

# Skills Demonstrated

- Windows Security Monitoring
- Splunk Search Processing Language (SPL)
- Log Analysis
- Incident Investigation
- Threat Hunting
- IOC Analysis
- Phishing Analysis
- OSINT
- Digital Forensics
- MITRE ATT&CK Mapping
- Alert Triage
