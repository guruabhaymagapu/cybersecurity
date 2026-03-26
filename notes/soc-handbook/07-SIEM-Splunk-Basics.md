# 📘 Module 07 – SIEM Splunk Basics 

---

## 1. What is SIEM?

SIEM stands for:

**Security Information and Event Management**

SIEM is a security solution used to:

* Collect logs from multiple systems
* Monitor security events
* Detect suspicious activity
* Generate alerts
* Assist in incident investigation
* Support incident response

Example SIEM Tool:

* **Splunk**

---

## 2. Why SIEM is Important in SOC?

SOC Analysts use SIEM to:

* Monitor authentication activity
* Detect unauthorized access
* Detect malware execution
* Detect privilege escalation
* Monitor user behavior
* Investigate security incidents

SIEM provides:

* Centralized log monitoring
* Real-time visibility
* Alert generation
* Investigation capability

---

## 3. SIEM Workflow

```
Log Collection → Parsing → Normalization → Indexing → Detection → Alerting → Investigation
```

---

## 4. Splunk Architecture Components

Splunk consists of:

* Universal Forwarder → Collects logs from endpoints
* Indexer → Stores and indexes logs
* Search Head → Used for searching logs
* Deployment Server → Manages forwarders
* License Master → Controls Splunk license

---

## 5. Log Ingestion in Splunk

Logs are collected from:

* Windows Endpoints
* Linux Systems
* Firewalls
* Routers
* IDS / IPS
* Web Servers
* Network Devices
* Antivirus Systems

---

## 6. Important Splunk Data Terms

| Term       | Meaning               |
| ---------- | --------------------- |
| Host       | Log generating system |
| Source     | Log file location     |
| Sourcetype | Log format            |
| Index      | Log storage location  |
| Event      | Individual log entry  |
| Field      | Information extracted |

---

## 7. SPL (Search Processing Language)

Splunk uses SPL to:

* Search logs
* Filter events
* Perform investigation
* Detect suspicious activity

---

### Basic SPL Commands

```spl
search
table
fields
rename
sort
dedup
```

---

### Time-Based Searching

```spl
earliest=-24h
earliest=-1h
earliest=-15m
latest=now
```

---

## 8. Transforming Commands

Used to analyze logs:

```spl
stats
chart
timechart
top
rare
count
```

Example:

```spl
stats count by src_ip
```

---

## 9. Common Fields Used in SOC Investigation

SOC Analysts analyze:

* username
* src_ip
* dest_ip
* EventCode
* action
* status
* process_name
* port
* protocol
* timestamp

---

## 10. Windows Logs in Splunk

| Event ID | Meaning          |
| -------- | ---------------- |
| 4624     | Successful Login |
| 4625     | Failed Login     |
| 4740     | Account Locked   |
| 4672     | Admin Privileges |
| 4688     | Process Created  |
| 1102     | Log Cleared      |

---

## 11. What is Detection in SIEM?

Detection means:

Identifying suspicious behavior from logs using SPL queries.

Examples:

* Unauthorized login
* Privilege escalation
* Suspicious process execution
* Login at unusual time

---

## 12. What is an Alert in Splunk?

Alert is a notification generated when:

Suspicious activity is detected in logs.

---

## 13. Types of Alerts

* Scheduled Alerts
* Real-Time Alerts

---

## 14. Alert Trigger Conditions

Examples:

* Login failure count exceeds threshold
* Unauthorized access detected
* Suspicious process execution

---

## 15. Alert Triage Process

SOC Analyst should:

1. Check alert details
2. Verify username
3. Check source IP
4. Check timestamp
5. Validate activity
6. Confirm false positive
7. Escalate if required

---

## 16. False Positive

Alert generated for normal activity.

Example:

User enters wrong password multiple times.

---

## 17. True Positive

Alert generated for malicious activity.

Example:

Unauthorized login attempt.

---

## 18. Importance of Time Synchronization

All systems must have:

Same time settings for accurate investigation.

Helps in:

* Event correlation
* Timeline analysis

---

## 19. SIEM Role in SOC

SIEM helps SOC Analysts to:

* Detect attacks
* Investigate incidents
* Monitor user behavior
* Identify compromised accounts
* Escalate security incidents

---

## 20. What is Log Parsing?

Log parsing is the process of converting raw machine-generated log data into a structured format so that it can be searched and analyzed easily.

Raw logs are usually unstructured and difficult to understand directly.

Parsing helps extract meaningful fields such as:

- Username  
- IP Address  
- Event Type  
- Timestamp  
- Port Number  
- Status (Success/Failure)

Parsed logs improve investigation speed and detection accuracy.

---

## 21. What is Log Normalization?

Log normalization is the process of converting logs from different devices into a common and standardized format.

Different devices generate logs in different structures.

Normalization ensures:

- Consistent field names
- Unified log format
- Better search results
- Improved correlation

It helps SIEM tools analyze logs from multiple sources efficiently.

---

## 22. What are Knowledge Objects in SIEM?

Knowledge Objects are reusable configurations used inside SIEM tools to organize and analyze data.

Common Knowledge Objects include:

- Saved Searches
- Event Types
- Tags
- Lookups
- Dashboards
- Alerts

They help SOC analysts automate detection and improve monitoring efficiency.

---

## 23. What is Event Correlation?

Event correlation is the process of linking multiple log events together to identify a possible security incident.

Single log events may not indicate an attack.

Example:

- Multiple failed logins
- Followed by successful login
- Followed by admin privilege usage

This sequence may indicate a brute-force attack.

Correlation helps detect complex attack patterns.

---

## 24. Types of Detection in SIEM

### a) Signature-Based Detection

Detects attacks using known patterns.

Example:

Known malware hash detection.

---

### b) Threshold-Based Detection

Detects suspicious activity based on count or limit.

Example:

More than 5 failed login attempts.

---

### c) Behavior-Based Detection

Detects abnormal user behavior.

Example:

Login from unusual geographic location.

---

### d) Baseline Deviation Detection

Detects activity that deviates from normal behavior.

Example:

User downloading large amount of data suddenly.

---

## 25. What is Log Retention?

Log retention is the process of storing logs for a specific period of time for future investigation.

Logs are stored for:

- Incident investigation
- Compliance requirements
- Legal purposes
- Forensic analysis

Retention helps SOC teams analyze past incidents effectively.

---

