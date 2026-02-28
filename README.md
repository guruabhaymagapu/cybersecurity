# 🛡️ # SOC L1 Home Lab – Networking, Linux & SIEM

## 📌 Overview

This repository contains structured hands-on lab notes designed for aspiring **SOC L1 (Security Operations Center) Analysts**.

The objective of this knowledge base is to:

* Build foundational networking knowledge
* Develop Linux investigation skills
* Understand SIEM log ingestion & monitoring
* Perform detection engineering using Splunk
* Simulate real-world attack use-cases such as brute-force login attempts

All labs were implemented in a local home lab environment and documented from a SOC analyst investigation perspective.

---

# 📡 1. Networking Fundamentals for SOC Analysts

Understanding networking is critical in SOC environments for:

* Log analysis
* Traffic investigation
* Incident triage
* Identifying lateral movement
* Investigating brute-force attacks
* Understanding VLAN segmentation in enterprise environments

---

## 🔹 Physical Network Topology

Basic enterprise network simulation includes:

* Router
* Switch
* End-user systems (PCs)
* Application Server

All devices communicate within:

```
Network: 192.168.1.0/24
Default Gateway: 192.168.1.1
```

SOC Relevance:

Analysts frequently investigate:

* Source IP Address
* Destination IP Address
* Gateway routing behavior
* Internal vs External communication

---

## 🔹 DHCP (Dynamic Host Configuration Protocol)

DHCP dynamically assigns:

* IP Address
* Default Gateway
* DNS Server

SOC Use-Case:

Helps in:

* Mapping IP → Endpoint during investigations
* Identifying rogue devices in internal network
* Tracking suspicious IP lease assignments

---

## 🔹 Subnetting & Network Segmentation

Example segmentation:

| Subnet           | Purpose |
| ---------------- | ------- |
| 192.168.1.0/25   | Users   |
| 192.168.1.128/25 | Servers |

SOC Relevance:

Segmentation helps:

* Restrict lateral movement
* Identify unauthorized cross-network communication
* Monitor sensitive server zones separately

---

## 🔹 VLAN Segmentation (Layer 2 Security)

Example VLAN Design:

| VLAN ID | Network Zone |
| ------- | ------------ |
| VLAN 10 | Users        |
| VLAN 20 | Servers      |
| VLAN 99 | Management   |

SOC Relevance:

SOC Analysts monitor:

* Unauthorized VLAN hopping attempts
* Traffic between user & server segments
* Access to management VLAN

---

## 🔹 Inter-VLAN Routing (Router-on-a-Stick)

Allows controlled communication between VLANs using:

* 802.1Q trunking
* Router subinterfaces

SOC Use-Case:

Helps detect:

* Policy violations
* Unauthorized internal access
* Server communication from user VLAN

---

## 🔹 Wireless Network Monitoring

Wireless network configured with:

* WPA2 Authentication
* DHCP Enabled

SOC Relevance:

Used to monitor:

* Rogue wireless clients
* Unauthorized SSID connections
* DHCP lease anomalies

---

# 🐧 2. Linux Fundamentals for SOC Investigation

(Based on OverTheWire Bandit Wargame)

## 🔹 SSH Remote Access

Used for:

* Secure remote system login
* Accessing compromised systems
* Investigating production Linux servers

---

## 🔹 File System Navigation

Commands Used:

```
ls
cd
cat
```

SOC Use-Case:

* Locate suspicious files
* Investigate malware drop locations
* Review user directories

---

## 🔹 Hidden File Detection

```
ls -al
```

SOC Relevance:

Attackers often store:

* Persistence scripts
* Malicious binaries
* SSH backdoors

Inside hidden files.

---

## 🔹 File Type Identification

```
find . -type f | xargs file
```

Helps detect:

* Executables disguised as text files
* Suspicious binaries
* Encoded payloads

---

## 🔹 Permission-Based File Discovery

```
find / -type f -user <user> -group <group> -size <size>
```

SOC Relevance:

Used to detect:

* Unauthorized privilege escalation
* Suspicious files created by attackers
* Persistence mechanisms

---

# 📊 3. SIEM Monitoring using Splunk

SIEM enables:

* Log aggregation
* Security monitoring
* Threat detection
* Alert generation
* Incident response

---

## 🔹 Windows Log Ingestion

Windows Security Logs onboarded into:

```
Index: windows
Source: WinEventLog:Security
```

SOC Use-Case:

Helps monitor:

* Login attempts
* Account lockouts
* Privilege changes
* Authentication failures

---

## 🚨 Brute-Force Detection

(EventID: 4625 – Failed Logon)

Detection Logic:

* Multiple failed login attempts
* Same username
* Same IP address

### SPL Detection Query

```spl
index=windows source="WinEventLog:Security" "<EventID>4625</EventID>"
| rex field=_raw "<Data Name='TargetUserName'>(?<TargetUserName>[^<]+)</Data>"
| rex field=_raw "<Data Name='IpAddress'>(?<IpAddress>[^<]+)</Data>"
| stats count by TargetUserName IpAddress
| where count >= 5
| sort -count
```

SOC Analyst Insight:

Repeated authentication failures may indicate:

* Password spraying
* Credential stuffing
* Brute-force attack attempts

---

## 🔐 Account Lockout Detection

(EventID: 4740)

Indicates:

* User account has been locked due to multiple failed logins

### SPL Detection Query

```spl
index=windows source="WinEventLog:Security" "<EventID>4740</EventID>"
| rex field=_raw "<Data Name='TargetUserName'>(?<TargetUserName>[^<]+)</Data>"
| stats count by TargetUserName
| where count >= 1
| sort -count
```

SOC Relevance:

May indicate:

* Compromised credentials
* Insider threat activity
* Brute-force attack success

---

# 📌 Key SOC Concepts Covered

* Network Segmentation
* VLAN Security
* DHCP Monitoring
* Authentication Log Analysis
* Windows Event Monitoring
* Brute-Force Detection
* Account Lockout Monitoring
* Linux File Investigation
* SIEM Alerting
* Dashboard Monitoring

---

# 🎯 Outcome

After completing these labs, you should be able to:

✔ Understand enterprise network architecture
✔ Investigate authentication failures
✔ Detect brute-force login attempts
✔ Monitor account lockouts
✔ Navigate Linux systems during incidents
✔ Create SIEM alerts using SPL
✔ Visualize security events in dashboards

---

If you want next, I can give you:

✅ Repo folder structure for beginners
✅ SOC Interview Questions from this README
✅ Next README for Threat Detection Use-Cases

Tell me what you want to prepare next.
