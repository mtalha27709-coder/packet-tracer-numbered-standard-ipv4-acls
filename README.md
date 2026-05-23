# Packet Tracer - Configure Numbered Standard IPv4 ACLs

## 📌 Project Overview
This project demonstrates the configuration, application, and verification of numbered standard IPv4 Access Control Lists (ACLs) using Cisco Packet Tracer.

The lab focuses on implementing security policies to control network traffic between multiple subnets while maintaining permitted communication across the network.

---

## 🎯 Objectives
- Plan ACL implementation based on network security policies
- Configure numbered standard IPv4 ACLs
- Apply ACLs to router interfaces
- Verify ACL functionality using connectivity tests
- Analyze ACL packet matches and filtering behavior

---

## 🖥️ Network Topology
The network consists of:
- 3 Cisco Routers (R1, R2, R3)
- Multiple LAN networks
- A Web Server
- End devices (PC1, PC2, PC3)

### Network Policies
#### Policy 1 (R2)
- Deny access from `192.168.11.0/24`
- Restrict access to the WebServer network `192.168.20.0/24`
- Permit all other traffic

#### Policy 2 (R3)
- Deny communication from `192.168.10.0/24`
- Restrict access to `192.168.30.0/24`
- Permit all other traffic

---

## ⚙️ Technologies Used
- Cisco Packet Tracer
- Cisco IOS CLI
- IPv4 Networking
- Standard ACLs
- EIGRP Routing

---

## 🔐 ACL Configuration

### R2 ACL Configuration
```bash
access-list 1 deny 192.168.11.0 0.0.0.255
access-list 1 permit any

interface GigabitEthernet0/0
ip access-group 1 out
```

### R3 ACL Configuration
```bash
access-list 1 deny 192.168.10.0 0.0.0.255
access-list 1 permit any

interface GigabitEthernet0/0
ip access-group 1 out
```

---

## ✅ Verification Tests

| Test | Result |
|------|--------|
| PC1 → PC2 | Successful |
| PC1 → WebServer | Successful |
| PC2 → WebServer | Blocked |
| PC1 → PC3 | Blocked |
| PC2 → PC3 | Successful |
| PC3 → WebServer | Successful |

---

## 📊 Key Learning Outcomes
- Understanding standard ACL behavior
- ACL placement best practices
- Traffic filtering using source IP addresses
- Verifying ACL effectiveness
- Network segmentation and access control

---

## 📁 Project Files
- Packet Tracer topology file
- Router configurations
- Verification screenshots
- ACL testing results

---

## 🚀 Author
Muhammad Talha

Cybersecurity & Network Security Enthusiast
