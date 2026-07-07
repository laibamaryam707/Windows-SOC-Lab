**Process Creation**
index=sysmon EventCode=1
| stats count

**purpose**
Counts Sysmon Process Creation Events
