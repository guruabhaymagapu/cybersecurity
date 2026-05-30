## 📘 SOC Analyst Playbook 

---

## 🔹 1. What is a SOC Playbook?

A SOC Playbook is a **documented step-by-step investigation workflow** followed by analysts when a security alert is triggered in a SIEM.

It helps to:

* Standardize alert investigation
* Reduce Mean Time To Respond (MTTR)
* Avoid missing investigation steps
* Maintain consistency across analysts
* Support proper escalation
* Ensure audit-ready documentation

---

## 🔹 2. SOC L1 Analyst Responsibilities

SOC L1 Analysts are responsible for:

* Monitoring SIEM dashboards
* Alert triage
* Log analysis
* Event correlation
* Identifying Indicators of Compromise (IOCs)
* Identifying false positives
* Initial threat validation
* Ticket creation & documentation
* Incident categorization
* Initial containment suggestion
* Escalation to L2 / L3 teams

---

## 🔹 3. Alert Triage Workflow (Must Know)

### Step 1 – Alert Intake

* Review alert name
* Detection rule triggered
* Time of alert
* Affected asset
* Source IP / Username

---

### Step 2 – Context Gathering

* Hostname
* Logged-in user
* Asset criticality
* Location
* Business unit

---

### Step 3 – Log Correlation

Check:

* Windows Event Logs
* Firewall logs
* Authentication logs
* Process logs
* Network traffic logs

---

### Step 4 – IOC Identification

Examples:

* Suspicious IP address
* Unknown executable
* Privileged account login
* Encoded PowerShell execution
* New service creation

---

### Step 5 – False Positive Check

Verify:

* Approved admin activity
* Scheduled tasks
* Patch deployment
* Backup jobs
* Vulnerability scan
* IT maintenance activity

---

### Step 6 – Severity Classification

| Severity | Description                  |
| -------- | ---------------------------- |
| Low      | No threat activity           |
| Medium   | Suspicious behavior          |
| High     | Confirmed malicious activity |
| Critical | Active compromise            |

---

### Step 7 – Decision Making

* Close as false positive
* Monitor
* Containment suggestion
* Escalate to L2

---

---

# 🔍 4. Investigation Playbooks

---

## 🛑 A. Brute Force Attack

Event IDs:

* 4625 – Failed Login
* 4624 – Successful Login
* 4740 – Account Lockout

Investigate:

* Source IP
* Logon Type
* Username targeted
* Login success after failures
* Internal vs External source
* Geo-location
* Account lockout

Escalate if:

* Admin account targeted
* Success after failure
* Multiple hosts targeted

---

## 🔐 B. Suspicious Successful Login

Event ID:

* 4624

Check:

* Logon Type 3 / 10
* New device login
* After business hours login
* VPN usage
* Impossible travel
* Privileged account usage

---

## 🔼 C. Privilege Escalation

Event IDs:

* 4672
* 4728
* 4732

Check:

* Who granted privileges
* Group modified
* Change ticket
* Unauthorized access

---

## 🦠 D. Malware Detection

Investigate:

* Affected endpoint
* File path
* Hash value
* Process name
* Parent process
* Registry persistence
* Network communication

---

## ⚙️ E. Suspicious Process Execution

Event ID:

* 4688

Check:

* PowerShell encoded commands
* Execution from temp folder
* Script execution
* LOLBins usage

Examples:

* powershell.exe
* cmd.exe
* wmic.exe
* mshta.exe

---

## 🌐 F. RDP Login Activity

Event IDs:

* 4624 (Logon Type 10)
* 4778
* 4779

Check:

* External login
* Repeated RDP attempts
* Admin login
* Non-business hours access

---

## 🧰 G. New Service Installation

Event ID:

* 7045

Check:

* Service name
* Executable path
* Account used
* Persistence indicator

---

## 📤 H. Data Exfiltration

Check:

* Unusual outbound traffic
* Upload spikes
* Destination IP
* Unknown ports
* Cloud storage usage

---

## 🔌 I. USB Device Activity

Event ID:

* 4663

Check:

* Device name
* File copy activity
* Sensitive file access

---

## 👤 J. Account Lockout

Event ID:

* 4740

Check:

* Caller computer name
* Source machine
* Password spray attempt
* Service account failure

---

---

# 🔹 5. Ticket Documentation (Mandatory)

Include:

* Alert Name
* Affected Asset
* Source IP
* Username
* Event ID
* Investigation Steps
* Findings
* IOC Identified
* Severity
* Analyst Action
* Escalation Decision

---

---

# 🔹 6. Escalation Criteria

Escalate if:

* Malware persistence detected
* Privileged account compromise
* External unauthorized login
* Lateral movement suspected
* Multiple host compromise
* Command & Control communication

---

---

# 🔹 7. Incident Categories

* Malware
* Phishing
* Unauthorized Access
* Brute Force
* Data Exfiltration
* Insider Threat
* Policy Violation

---


# 🔹 8. Key Metrics SOC Analysts Should Know

* MTTA – Mean Time To Acknowledge
* MTTR – Mean Time To Respond
* False Positive Rate
* True Positive Rate
* Dwell Time

---

---

# 🔹 9. Shift Handover Notes

Must include:

* Open incidents
* Escalated tickets
* Ongoing investigations
* Pending containment
* Observations

---

---

# 🔹 10. SOC L1 Analyst Expected Skills

* SIEM Monitoring
* Log Correlation
* Windows Event Analysis
* Network Log Analysis
* IOC Identification
* Basic Threat Hunting
* Documentation
* Incident Classification

---

---

# ✅ Module 10 Outcome

After completing this module, a SOC L1 Analyst should be able to:

✔ Investigate SIEM alerts
✔ Perform log correlation
✔ Identify malicious activity
✔ Detect false positives
✔ Document findings
✔ Suggest containment
✔ Escalate incidents properly

---

