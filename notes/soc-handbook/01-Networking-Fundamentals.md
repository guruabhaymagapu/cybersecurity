📘 01 – Networking Fundamentals 

# 🔹 SECTION 1 – Why Networking Exists

---

## 1. What is Communication?

Communication is the process of:

* Sending data
* Receiving data

between two or more systems.

Example:

When you send an email or open a website, your device is communicating with another system over a network.

SOC Relevance:

Cyber attacks occur when unauthorized systems communicate with internal devices.
SOC analysts monitor communication patterns to detect malicious activity.

---

## 2. What is Data?

Data is any form of information that can be:

* Stored
* Processed
* Transmitted

Examples:

* Text
* Images
* Videos
* Login Credentials
* Application Logs

SOC Relevance:

Attackers often try to:

* Steal sensitive data
* Modify stored data
* Transfer data outside the network

Monitoring data movement is a key responsibility of SOC analysts.

---

## 3. Why Devices Need to Communicate?

Devices communicate in order to:

* Share files
* Access applications
* Send emails
* Browse websites
* Authenticate users

Example:

When you log in to a company system, your computer communicates with an authentication server to verify your credentials.

SOC Relevance:

Unauthorized communication may indicate:

* Malware infection
* Data exfiltration
* Unauthorized access attempts

---

## 4. What is a Computer Network?

A Computer Network is a group of interconnected devices that communicate with each other to:

* Exchange data
* Share resources
* Access services

Devices in a network may include:

* Computers
* Servers
* Routers
* Switches
* Mobile devices

SOC Relevance:

Understanding how devices are connected helps analysts:

* Identify suspicious traffic
* Investigate internal attacks
* Monitor network behavior

---

# 🔹 SECTION 2 – Types of Networks

---

## 5. LAN – Local Area Network

A LAN is a network that connects devices within a:

* Home
* Office
* Organization
* Building

All devices in LAN communicate using internal IP addresses.

SOC Relevance:

Internal attacks such as:

* Insider threats
* Lateral movement

usually occur within LAN environments.

---

## 6. WAN – Wide Area Network

A WAN connects multiple LANs across:

* Cities
* Countries
* Continents

Example:

Internet is the largest WAN.

SOC Relevance:

SOC teams monitor WAN traffic to detect:

* External attacks
* Malicious incoming connections
* Suspicious outbound communication

---

## 7. MAN – Metropolitan Area Network

MAN connects networks within a:

* City
* Metropolitan area

Example:

A university connecting multiple campus networks.

SOC Relevance:

Used in enterprise environments with geographically distributed branches.

---

## 8. Internet vs Intranet

### Internet

* Public network
* Accessible globally
* Uses public IP addresses

SOC Use:

Used to monitor:

* External threats
* Phishing domains
* Malware communication

---

### Intranet

* Private internal network
* Accessible only within an organization
* Uses private IP addresses

SOC Use:

Helps detect:

* Internal attacker movement
* Unauthorized internal access

---

# 🔹 SECTION 3 – Basic Network Devices

---

## 9. What is a Client?

A Client is a system that:

Requests services from another system.

Example:

* Laptop accessing email
* Mobile phone browsing website

SOC Relevance:

Compromised client systems can be used by attackers to:

* Move laterally
* Launch internal attacks

---

## 10. What is a Server?

A Server is a system that:

Provides services or resources to clients over a network.

Types of Servers:

* Web Server
* File Server
* Mail Server
* Authentication Server

SOC Relevance:

Attackers often target servers to:

* Steal data
* Gain persistence
* Escalate privileges

---

## 11. What is a Switch?

A Switch is a Layer 2 network device used to:

* Connect devices inside LAN
* Forward data using MAC address

SOC Relevance:

Switch logs help detect:

* Unauthorized device connections
* Internal network scanning

---

## 12. What is a Router?

A Router is a Layer 3 network device used to:

* Connect different networks
* Forward data packets using IP address

Router acts as:

Default Gateway

SOC Relevance:

Routers help analysts identify:

* Source Network
* Destination Network
* Suspicious outbound traffic

---

## 13. What is a Firewall?

A Firewall is a security device that:

* Monitors network traffic
* Allows or blocks traffic based on rules

SOC Relevance:

Firewalls generate logs used by SOC analysts to detect:

* Unauthorized access
* Malicious traffic

---



## **Q14. What is a MAC Address?**

A **MAC Address (Media Access Control Address)** is a **physical address** assigned to a network interface card (NIC) of a device.

It is:

* Hardcoded by the manufacturer
* Unique for every device
* Used for communication inside a local network (LAN)

---

### **MAC Address Format**

```id="6f2tq9"
00:1A:2B:3C:4D:5E
```

* 12-digit hexadecimal value
* First 6 digits → Manufacturer
* Last 6 digits → Device ID

---

### **SOC Analyst Note**

MAC addresses are useful for:

* Identifying devices in internal network investigations
* Tracking unauthorized devices inside enterprise LAN

---

## **Q15. What is an IP Address?**

An **IP Address (Internet Protocol Address)** is a **logical address** assigned to every device in a network to identify it and enable communication.

It helps in:

* Sending data
* Receiving data
* Identifying source and destination devices

---

### **Example**

```id="qz7k2x"
192.168.1.10
```

Without an IP address:

> A device cannot communicate over a network.

---

## **Q16. Difference Between MAC Address and IP Address**

| Feature     | MAC Address         | IP Address                       |
| ----------- | ------------------- | -------------------------------- |
| Type        | Physical Address    | Logical Address                  |
| Assigned By | Manufacturer        | Network Admin / ISP              |
| Used In     | Local Network (LAN) | Internet / Network Communication |
| Changeable  | No                  | Yes                              |
| Format      | Hexadecimal         | Decimal (IPv4)                   |

---

### Simple Understanding:

* MAC Address → Permanent device identity
* IP Address → Temporary network identity

---

## **Q17. Public IP vs Private IP**

---

### **Public IP Address**

* Used to communicate over the Internet
* Assigned by ISP
* Globally unique

Example:

```id="k9a4pd"
8.8.8.8
```

---

### **Private IP Address**

* Used inside internal networks
* Not accessible from Internet
* Assigned by router or network admin

Example:

```id="9zlm1w"
192.168.0.5
```

---

### **Private IP Ranges**

| Class | Range                         |
| ----- | ----------------------------- |
| A     | 10.0.0.0 – 10.255.255.255     |
| B     | 172.16.0.0 – 172.31.255.255   |
| C     | 192.168.0.0 – 192.168.255.255 |

---

### **SOC Analyst Importance**

SOC analysts use Public and Private IPs to:

* Identify internal vs external threats
* Track attacker source
* Detect suspicious outbound connections

---



## **Q18. What is IPv4?**

**IPv4 (Internet Protocol Version 4)** is the most widely used IP addressing system used to identify devices on a network.

It uses:

* **32-bit address**
* Written in **decimal format**

---

### **IPv4 Format**

```id="m8y2ks"
192.168.1.1
```

IPv4 address is divided into:

* Network portion
* Host portion

---

### **Total IPv4 Addresses**

```id="z5trnq"
2^32 = 4.3 Billion Addresses
```

Due to the rapid growth of the Internet, IPv4 addresses are almost exhausted.

---

### **SOC Analyst Note**

Most enterprise networks still operate on **IPv4**, so SOC analysts frequently monitor IPv4 traffic in:

* Firewall logs
* SIEM dashboards
* Network alerts

---

## **Q19. What is IPv6?**

**IPv6 (Internet Protocol Version 6)** was introduced to overcome the limitations of IPv4.

It uses:

* **128-bit address**
* Written in **hexadecimal format**

---

### **IPv6 Format**

```id="6vkj1p"
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

---

### **Total IPv6 Addresses**

```id="9xq2cb"
2^128 ≈ 340 Undecillion Addresses
```

IPv6 provides:

* Larger address space
* Better security
* Improved routing efficiency

---

### **SOC Analyst Note**

Modern cloud environments are gradually adopting IPv6, so analysts must understand IPv6 traffic patterns.

---

## **Q20. Difference Between IPv4 and IPv6**

| Feature           | IPv4     | IPv6            |
| ----------------- | -------- | --------------- |
| Address Size      | 32-bit   | 128-bit         |
| Format            | Decimal  | Hexadecimal     |
| Address Count     | Limited  | Extremely Large |
| Security          | Optional | Built-in        |
| NAT Required      | Yes      | No              |
| Header Complexity | Simple   | More Efficient  |

---

### **Simple Understanding**

* IPv4 → Limited address space
* IPv6 → Massive address space for future Internet growth

---


## **Q21. What is a Packet?**

A **Packet** is the smallest unit of data that is transmitted over a network.

When data (like a message or website request) is sent:

> It is broken into smaller pieces called packets.

Each packet contains:

* Source IP address
* Destination IP address
* Actual data
* Protocol information

SOC analysts inspect packets to detect:

* Malicious traffic
* Data exfiltration
* Suspicious connections

---

## **Q22. What is a Protocol?**

A **Protocol** is a set of rules that define how data is transmitted over a network.

Protocols ensure:

* Correct delivery of data
* Reliable communication
* Error detection

Examples:

* HTTP
* HTTPS
* TCP
* UDP
* DNS

---

## **Q23. TCP vs UDP (Basic Comparison)**

| Feature        | TCP                 | UDP             |
| -------------- | ------------------- | --------------- |
| Connection     | Connection-oriented | Connectionless  |
| Reliability    | Reliable            | Unreliable      |
| Speed          | Slower              | Faster          |
| Error Checking | Yes                 | No              |
| Use Case       | Web browsing        | Video streaming |

SOC Note:
Attackers often use UDP for faster communication during attacks.

---

## **Q24. What is a Port Number?**

A **Port Number** identifies a specific service running on a device.

It helps the system understand:

> Which application should receive the incoming data.

Example:

* Port 80 → HTTP
* Port 443 → HTTPS
* Port 22 → SSH
* Port 53 → DNS

SOC analysts monitor port activity to detect:

* Unauthorized services
* Suspicious connections

---

## **Q25. What is a Default Gateway?**

A **Default Gateway** is the device that connects a local network to other networks (like the Internet).

Usually:

> It is the Router IP address.

Example:

```id="gw1p8s"
192.168.1.1
```

---

## **Q26. What is DNS?**

**DNS (Domain Name System)** converts:

> Domain names → IP addresses

Example:

```id="8m7rqs"
google.com → 142.250.183.14
```

Without DNS:
You would need to remember IP addresses of websites.

---

## **Q27. What is HTTP & HTTPS?**

| Protocol | Meaning                            | Security   |
| -------- | ---------------------------------- | ---------- |
| HTTP     | Hypertext Transfer Protocol        | Not Secure |
| HTTPS    | Hypertext Transfer Protocol Secure | Encrypted  |

HTTPS uses encryption to protect:

* Login details
* Sensitive information

SOC monitors HTTP traffic for:

* Suspicious downloads
* Malware communication

---

## **Q28. What Happens When You Open a Website?**

Steps:

1. User enters website name
2. DNS converts domain to IP
3. Browser sends request
4. Server responds
5. Data sent as packets
6. Browser displays webpage

---

## **Q29. OSI Model (High-level Introduction)**

OSI Model has **7 layers**:

1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

It explains:

> How data travels from one system to another.

---

## **Q30. TCP/IP Model**

TCP/IP Model has **4 layers**:

1. Network Interface
2. Internet
3. Transport
4. Application

It is the practical model used in real networks.

---

## **Q31. Encapsulation (Step-by-step)**

Encapsulation is:

> Process of adding headers to data before transmission.

Steps:

1. Application Layer → Data
2. Transport Layer → Segment
3. Network Layer → Packet
4. Data Link Layer → Frame
5. Physical Layer → Bits

---

## **Q32. What is a Subnet Mask?**

Subnet Mask defines:

> Network portion and Host portion of an IP address.

Example:

```id="7ps1ac"
255.255.255.0
```

---

## **Q33. What is Subnetting?**

Subnetting divides a large network into smaller networks for:

* Better performance
* Improved security
* Reduced congestion

---

## **Q34. What is Subnet?**

A **Subnet** is a smaller network created from a main network.

---

## **Q35. What is Network Segmentation?**

Network Segmentation divides a network into smaller isolated sections.

Example:

* HR Network
* Finance Network
* IT Network

---

## **Q36. Why Network Segmentation is Important?**

It helps:

* Improve security
* Control access
* Reduce malware spread

---

## **Q37. What is VLAN?**

**VLAN (Virtual Local Area Network)** logically separates devices into different networks within the same physical network.

---

## **Q38. Why Segmentation Prevents Attacks?**

If one segment is infected:

> Attack cannot spread to other segments easily.

Prevents:

* Lateral movement
* Internal attacks

---

## **Q39. Source IP vs Destination IP in Logs**

| Field          | Meaning  |
| -------------- | -------- |
| Source IP      | Sender   |
| Destination IP | Receiver |

SOC uses these fields to:

* Track attacker
* Identify target system

---

## **Q40. Why Ports Matter in Alerts?**

Ports help SOC analysts:

* Identify services under attack
* Detect unauthorized access
* Analyze malicious activity

---

## **Q41. How SOC Uses Networking Knowledge**

SOC Analysts use networking to:

* Investigate incidents
* Analyze logs
* Detect threats
* Track attacker behavior

---


For a **SOC L1 – Networking Fundamentals**, what you’ve covered till **Q41** is already:

✅ Correct
✅ In logical flow
✅ Interview-relevant
✅ Enough for log analysis understanding
✅ Enough for SIEM alert investigation

But… from an actual **SOC investigation perspective**, you are still missing a few **very important operational networking concepts** that analysts *regularly see in logs*.

These are not CCNA-level theory — these are **SOC-useful networking basics**.

---


## **Q42. What is NAT (Network Address Translation)?**

NAT converts:

> Private IP Address → Public IP Address

Used by routers to allow internal devices to access the Internet using one public IP.

SOC Importance:

* Helps track outbound traffic
* Used in identifying internal attacker behind public IP

---

## **Q43. What is ARP (Address Resolution Protocol)?**

ARP maps:

> IP Address → MAC Address

Used inside LAN to locate the physical device associated with an IP.

SOC Importance:

* ARP spoofing is a common internal attack technique

---

## **Q44. What is DHCP (Dynamic Host Configuration Protocol)?**

DHCP automatically assigns:

* IP Address
* Subnet Mask
* Default Gateway
* DNS Server

SOC Importance:
Helps identify:

* New devices joining network
* Unauthorized device connections

---

## **Q45. What is ICMP?**

ICMP is used for:

> Network diagnostics

Example:

* Ping command uses ICMP

SOC Importance:
Attackers use ICMP for:

* Network scanning
* Host discovery

---

## **Q46. What is a Three-Way Handshake?**

TCP connection setup process:

1. SYN
2. SYN-ACK
3. ACK

SOC Importance:
Incomplete handshakes may indicate:

* SYN Flood attack
* Port scanning

---

## **Q47. What is Network Traffic?**

Network Traffic = Data moving across a network.

Types:

* Inbound Traffic
* Outbound Traffic

SOC monitors traffic to detect:

* Data exfiltration
* Malware communication

---

## **Q48. What is Bandwidth vs Latency?**

| Term      | Meaning                |
| --------- | ---------------------- |
| Bandwidth | Data transfer capacity |
| Latency   | Delay in communication |

SOC Importance:
Sudden traffic spikes may indicate:

* DDoS attack
* Malware activity

---

