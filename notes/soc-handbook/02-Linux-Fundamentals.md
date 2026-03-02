
📘 02 – Linux Fundamentals (SOC Relevant)

## 🎯 Objective

This module covers Linux fundamentals required for a SOC L1 analyst to:

* Investigate authentication logs
* Analyze suspicious files
* Monitor user activity
* Identify persistence mechanisms
* Support basic incident response

---

# 1. What is Linux?

Linux is an open-source operating system widely used in:

* Enterprise servers
* Cloud environments
* Security tools
* SIEM infrastructure

SOC analysts frequently investigate Linux-based systems.

---

# 2. Linux Distributions (Distros)

A distribution is a customized version of Linux.

Common examples:

* Ubuntu
* CentOS
* Kali Linux

Different distros are used for servers, enterprise systems, and security testing.

---

# 3. Linux File System Structure

Linux follows a hierarchical directory structure.

```
/
├── home
├── var
├── etc
├── bin
├── tmp
```

Important SOC directories:

| Directory | Purpose                                     |
| --------- | ------------------------------------------- |
| /var/log  | System and authentication logs              |
| /etc      | Configuration files                         |
| /home     | User files                                  |
| /tmp      | Temporary files (often abused by attackers) |

---

# 4. Linux Terminal & Basic Commands

| Command | Purpose                |
| ------- | ---------------------- |
| pwd     | Show current directory |
| ls      | List files             |
| ls -la  | Show hidden files      |
| cd      | Change directory       |
| cat     | View file              |
| clear   | Clear terminal         |

---

# 5. File Permissions

Linux uses:

* r → Read
* w → Write
* x → Execute

Example:

```
-rwxr-xr--
```

Permission groups:

* Owner
* Group
* Others

SOC analysts check permissions for unauthorized access or privilege abuse.

---

# 6. User Management

Important files:

```
/etc/passwd
/etc/shadow
```

Commands:

* who
* whoami
* id
* last

SOC Use:

* Investigate suspicious user logins
* Check new account creation
* Identify privilege escalation

---

# 7. SSH (Secure Shell)

SSH is used to remotely access Linux systems securely.

SOC relevance:

* Investigate brute-force login attempts
* Monitor remote access activity

Authentication logs are typically found in:

```
/var/log/auth.log
```

or

```
/var/log/secure
```

---

# 8. Log Analysis in Linux

Important logs:

| Log File | Purpose                           |
| -------- | --------------------------------- |
| auth.log | Login attempts                    |
| syslog   | System events                     |
| secure   | Authentication logs (CentOS/RHEL) |

Common investigation command:

```
grep "Failed password" auth.log
```

---

# 9. Process Management

Commands:

* ps
* top
* htop
* kill
* kill -9

SOC Use:

* Identify suspicious processes
* Detect malware running in memory
* Kill malicious process

---

# 10. Networking Commands in Linux

| Command         | Purpose                 |
| --------------- | ----------------------- |
| ifconfig / ip a | Check IP address        |
| netstat         | View active connections |
| ss              | Show socket statistics  |
| ping            | Connectivity check      |

SOC Use:

* Detect suspicious outbound connections
* Identify unknown listening ports

---

# 11. File Investigation Commands

| Command | Purpose            |
| ------- | ------------------ |
| find    | Locate files       |
| file    | Identify file type |
| chmod   | Change permissions |
| chown   | Change ownership   |

Example:

```
find / -type f -name suspicious.sh
```

---

# 12. Hidden Files

Hidden files begin with:

```
.
```

Example:

```
.bashrc
```

Attackers often hide malicious scripts as hidden files.

---

# 13. Cron Jobs (Persistence Mechanism)

Cron is used to schedule tasks.

Check cron jobs:

```
crontab -l
```

SOC Importance:

Attackers may create cron jobs for persistence.

---

# 14. Sudo & Privilege Escalation

Sudo allows temporary root access.

Check sudo users:

```
cat /etc/sudoers
```

SOC analysts check:

* Unauthorized sudo usage
* Suspicious privilege escalation

---

# 15. Package Management (Basic Awareness)

Used to install or remove software.

Examples:

* apt (Ubuntu)
* yum (CentOS)

SOC relevance:

* Identify unauthorized software installation

---

# 16. Basic Forensic Awareness

SOC analysts may:

* Check file timestamps
* Identify modified files
* Look for unusual binaries in `/tmp`

Commands:

* ls -lt
* stat filename

---

