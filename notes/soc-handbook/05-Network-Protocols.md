# Module 05 – Network Protocols 

---

## 1. What is a Network Protocol?

A **network protocol** is a set of rules that define how data is transmitted between devices over a network.

Protocols determine:

* How data is formatted
* How data is transmitted
* How data is received
* How errors are handled

Protocols ensure successful communication between systems.

---

## 2. Why Network Protocols are Important in SOC?

SOC analysts analyze network protocols to:

* Detect malicious communication
* Identify unauthorized access
* Monitor network traffic
* Detect data exfiltration
* Investigate attacker activity
* Identify command and control (C2) communication

Understanding protocols helps detect cyber attacks.

---

## 3. Protocols and Port Numbers

Each protocol operates on a specific **port number**.

Port numbers help SOC analysts identify:

* Type of communication
* Service being used
* Suspicious or unauthorized activity

Example:

Access to RDP on port 3389 from unknown IP may indicate attack.

---

## 4. Common Network Protocols SOC Analysts Must Know

---

### 4.1 HTTP (HyperText Transfer Protocol)

* Port: 80
* Used for web communication
* Transfers website data in plain text
* Not secure

SOC Concern:

Attackers can intercept HTTP traffic.

---

### 4.2 HTTPS (HyperText Transfer Protocol Secure)

* Port: 443
* Secure version of HTTP
* Uses encryption (SSL/TLS)

SOC Concern:

Encrypted traffic may hide malicious activity.

---

### 4.3 FTP (File Transfer Protocol)

* Port: 21
* Used to transfer files
* No encryption

SOC Concern:

Sensitive files may be transferred insecurely.

---

### 4.4 SFTP (Secure File Transfer Protocol)

* Port: 22
* Secure file transfer
* Uses SSH encryption

---

### 4.5 SSH (Secure Shell)

* Port: 22
* Secure remote login

SOC Concern:

Multiple SSH login attempts may indicate brute-force attack.

---

### 4.6 Telnet

* Port: 23
* Remote login protocol
* Sends data in plain text

SOC Concern:

Highly insecure and often used by attackers.

---

### 4.7 DNS (Domain Name System)

* Port: 53
* Converts domain name to IP address

SOC Concern:

Used in:

* DNS tunneling
* Data exfiltration
* Malware communication

---

### 4.8 SMTP (Simple Mail Transfer Protocol)

* Port: 25
* Sends email

SOC Concern:

Phishing emails
Spam attacks
Malware delivery

---

### 4.9 POP3 (Post Office Protocol)

* Port: 110
* Receives emails

---

### 4.10 IMAP (Internet Message Access Protocol)

* Port: 143
* Retrieves emails from server

---

### 4.11 SNMP (Simple Network Management Protocol)

* Port: 161
* Used for network device monitoring

SOC Concern:

Unauthorized SNMP access may reveal system info.

---

### 4.12 DHCP (Dynamic Host Configuration Protocol)

* Port: 67 / 68
* Assigns IP addresses automatically

SOC Concern:

Rogue DHCP server attack.

---

### 4.13 ICMP (Internet Control Message Protocol)

* Used for ping command

SOC Concern:

Used in:

* Network scanning
* Ping flood attacks
* Reconnaissance

---

### 4.14 RDP (Remote Desktop Protocol)

* Port: 3389
* Remote system access

SOC Concern:

Brute-force attacks
Unauthorized access

---

### 4.15 SMB (Server Message Block)

* Port: 445
* File and printer sharing

SOC Concern:

Used in:

* Lateral movement
* Ransomware attacks

---

## 5. Secure vs Insecure Protocols

### Insecure Protocols

* HTTP
* FTP
* Telnet
* POP3

Transmit data in plain text.

---

### Secure Protocols

* HTTPS
* SFTP
* SSH
* IMAPS

Use encryption for secure communication.

---

## 6. Protocols Used in Cyber Attacks

Attackers commonly misuse:

* DNS → Data exfiltration
* ICMP → Network scanning
* SMB → Lateral movement
* RDP → Unauthorized access
* FTP → Data theft

SOC analysts monitor these protocols.

---

## 7. Protocol Identification in Logs

SOC analysts check:

* Source IP
* Destination IP
* Port Number
* Protocol used
* Connection status

To determine:

Normal or suspicious activity.

---

## 8. Protocol-Based Attack Indicators

Suspicious activities include:

* Repeated SSH login attempts
* RDP access from unknown country
* Excessive DNS requests
* SMB traffic between endpoints
* FTP usage in restricted network
* ICMP flood requests

---

## 9. Real-Time Protocol Monitoring in SOC

SOC analysts monitor:

* Network traffic
* Incoming connections
* Outgoing connections
* Remote login attempts
* File transfer activity

Using SIEM tools.

---

## 10. Importance of Protocol Knowledge in SIEM Alerts

SIEM alerts often contain:

* Port number
* Protocol used
* Connection attempt

Example:

Multiple failed RDP login attempts
Port: 3389

May indicate brute-force attack.

---

## 11. How Protocols Help in Incident Investigation

Protocols help SOC analysts:

* Identify attack method
* Detect unauthorized communication
* Track attacker movement
* Identify compromised systems
* Investigate malware activity

---

## 12. Common SOC Use Case

Alert:

Unusual outbound DNS traffic detected.

Investigation:

1. Check Source IP
2. Check destination domain
3. Check frequency of DNS requests
4. Identify suspicious pattern

Possible cause:

DNS tunneling attack.

---


## 13. Stateful vs Stateless Protocols

### Stateful Protocol

Maintains connection information during communication.

Example:

* TCP

SOC Relevance:

Attackers may hijack active sessions.

---

### Stateless Protocol

Does not maintain session information.

Example:

* UDP

SOC Relevance:

Used in:

* DNS attacks
* Amplification attacks
* Spoofing attacks

---

## 14. TCP Handshake (3-Way Handshake)

TCP uses connection-oriented communication.

Steps:

1. SYN → Client sends connection request
2. SYN-ACK → Server acknowledges
3. ACK → Client confirms

Connection established.

SOC Relevance:

Repeated SYN packets may indicate:

* SYN Flood Attack
* Port Scanning

---

## 15. Protocol Abuse by Attackers

Attackers misuse protocols for:

* Data exfiltration
* Remote access
* Network scanning
* Malware communication
* Lateral movement

Example:

* DNS → Tunneling
* ICMP → Data transfer
* SMB → Ransomware spread
* RDP → Unauthorized login

---

## 16. Why Protocol Knowledge is Important for SOC Analysts?

Protocol knowledge helps to:

* Understand SIEM alerts
* Investigate login attempts
* Detect suspicious traffic
* Track attacker communication
* Identify compromised systems
* Perform incident investigation

---



