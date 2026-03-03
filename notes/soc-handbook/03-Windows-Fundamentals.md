# 03 – Windows Fundamentals 

## 🎯 Objective

This module helps SOC L1 analysts understand:

* Windows system structure
* User authentication
* Event logs
* Process monitoring
* Network activity
* Persistence mechanisms

Windows is widely used in enterprise environments, and most security alerts originate from Windows endpoints.

---

# 1. What is Microsoft Windows?

Windows is a graphical operating system used to:

* Manage hardware
* Run applications
* Control user access
* Monitor system activity

SOC analysts frequently investigate alerts generated from Windows systems.

---

# 2. Windows File System (NTFS)

Windows uses NTFS (New Technology File System) to:

* Store files
* Control access
* Manage permissions

Important directories:

| Directory        | Purpose                |
| ---------------- | ---------------------- |
| C:\Windows       | System files           |
| C:\Users         | User data              |
| C:\Program Files | Installed applications |
| C:\Temp          | Temporary files        |

Attackers often hide malicious files in:

```
C:\Temp
```

---

# 3. Windows User Accounts

Types of accounts:

* Administrator
* Standard User
* Guest

SOC analysts check:

* Unauthorized user creation
* Privilege misuse
* Suspicious login activity

---

# 4. Authentication in Windows

Windows uses:

* Username
* Password

Successful or failed login attempts are recorded in:

> Windows Security Logs

---

# 5. Windows Event Viewer

Event Viewer is used to monitor:

* Login attempts
* System errors
* Application activity
* Security events

SOC analysts use Event Viewer to investigate incidents.

---

# 6. Important Windows Event Logs

| Log Type    | Description      |
| ----------- | ---------------- |
| Security    | Login attempts   |
| System      | OS activity      |
| Application | App-related logs |

---

# 7. Important Event IDs (SOC Perspective)

| Event ID | Description               |
| -------- | ------------------------- |
| 4624     | Successful Login          |
| 4625     | Failed Login              |
| 4740     | Account Lockout           |
| 4720     | User Account Created      |
| 4672     | Admin Privileges Assigned |

SOC analysts monitor these logs for suspicious behavior.

---

# 8. Process Monitoring

Processes are running programs in memory.

Use:

* Task Manager
* Command Prompt

Commands:

```
tasklist
```

SOC analysts check:

* Unknown processes
* High CPU usage
* Malware execution

---

# 9. Network Activity Monitoring

Check active connections:

```
netstat -ano
```

SOC Use:

* Detect suspicious outbound traffic
* Identify unknown IP connections
* Find open ports

---

# 10. Windows Services

Services run in the background.

Check services:

```
services.msc
```

SOC analysts check:

* Suspicious services
* Unauthorized startup services

---

# 11. Persistence Mechanisms

Attackers may maintain access using:

* Startup folder
* Scheduled tasks
* Registry entries

Check:

```
Task Scheduler
```

---

# 12. Windows Registry

Registry stores system configuration.

Attackers may create entries to:

* Run malware automatically

SOC analysts check registry for persistence.

---

# 13. Temporary Files

Temporary files stored in:

```
C:\Temp
```

Attackers often place:

* Malicious scripts
* Suspicious executables

---

# 14. Command Prompt Basics

| Command  | Purpose           |
| -------- | ----------------- |
| ipconfig | Check IP address  |
| netstat  | View connections  |
| tasklist | Running processes |
| whoami   | Current user      |

---

# 15. Windows Logs in SOC Investigation

SOC analysts investigate:

* Login failures
* Account lockouts
* Unauthorized account creation
* Privilege escalation
* Suspicious processes

These logs are ingested into SIEM tools for monitoring.

---

# 16. Account Lockout

Repeated failed login attempts may result in:

> Account Lockout

Logged as:

```
Event ID 4740
```

May indicate:

* Brute-force attack
* Unauthorized login attempt

---

# 17. Failed Login Detection

```
Event ID 4625
```

Indicates:

* Invalid password attempts
* Possible brute-force attack

---

# 18. Successful Login Monitoring

```
Event ID 4624
```

SOC analysts verify:

* Login time
* Source system
* User account

---

# 19. Privilege Escalation Monitoring

```
Event ID 4672
```

Indicates:

* Admin privileges assigned

SOC analysts investigate unauthorized privilege usage.

---

# 20. SOC Relevance

Windows fundamentals help SOC analysts to:

* Investigate login failures
* Detect brute-force attacks
* Identify suspicious processes
* Monitor user activity
* Detect persistence mechanisms
* Support incident response

---

