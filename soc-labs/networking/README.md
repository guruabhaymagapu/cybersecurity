# Networking Lab with Cisco Packet Tracer

## Objective
Set up environment for hands-on networking labs, starting with Packet Tracer simulations for cybersecurity fundamentals.

## Day 1 - Environment Setup
-  Created GitHub repo: cybersecurity  
-  Installed Cisco Packet Tracer
-  Folder structure: screenshots/ + README.md

## Day 2 — Network Topology (Physical Layer)

- Designed a basic physical network topology using a router, switch, PCs, and a server
- Connected all devices using copper straight-through cables
- Enabled router interface and verified physical connectivity by confirming active (green) links


## Day 3 – IP Addressing & Connectivity Testing

### Configuration
- Router IP: 192.168.1.1 /24
- PC1 IP: 192.168.1.10 /24
- PC2 IP: 192.168.1.11 /24
- Server IP: 192.168.1.20 /24
- Default Gateway (All hosts): 192.168.1.1

### Verification
- Successfully pinged router (192.168.1.1) from PC1, PC2, and Server


## Day 4 – DHCP Configuration

### Objective
-Configured DHCP on the router with a pool for the 192.168.1.0/24 network.
-Excluded static IP addresses and verified dynamic IP assignment.

### DHCP Settings
- PC0 received 192.168.1.10
- PC1 received 192.168.1.11
- Server received 192.168.1.12
- Default gateway assigned as 192.168.1.1
- DNS Server: 8.8.8.8

### Verification
- PCs and Server received IPs via DHCP
- Successful ping to router and between hosts

