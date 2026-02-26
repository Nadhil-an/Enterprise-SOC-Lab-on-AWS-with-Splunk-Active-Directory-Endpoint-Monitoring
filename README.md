# 🛡 Enterprise SOC Lab on AWS
### Splunk SIEM with Active Directory, Windows Endpoint & Web Server Monitoring

---
## 🏗 SOC Architecture Diagram

<p align="center">
  <img src="assets/soc architecture.png" width="900">
</p>



## 📌 Project Overview

This project demonstrates the design and implementation of a cloud-based **Enterprise Security Operations Center (SOC) Lab** hosted entirely on AWS.

The lab simulates a real-world enterprise environment where:

- Users authenticate through **Active Directory**
- A domain-joined **Windows Endpoint** generates security logs
- A **Web Server (DVWA)** simulates web application attacks
- All logs are centralized into **Splunk Enterprise (SIEM)**
- Controlled attacks are simulated using **Kali Linux**

The main goal of this project is to understand how enterprise security monitoring works in real-world organizations.

---

## 🎯 Project Objectives

- Design enterprise-style cloud infrastructure
- Implement centralized log monitoring using SIEM
- Simulate authentication and web-based attack scenarios
- Monitor and analyze suspicious activities
- Understand real SOC workflows and security operations

---

## 🏗 Architecture Components
---

The lab environment includes:

- AWS Custom VPC (Isolated cloud network)
- Windows Server (Active Directory)
- Domain-Joined Windows Endpoint
- Ubuntu Web Server with DVWA
- Splunk Enterprise (SIEM)
- Splunk Universal Forwarders
- Kali Linux (Attack Simulation Machine)

---

## 🔄 Log Flow Architecture
---

- Windows Endpoint → Splunk
- Active Directory → Splunk
- Web Server → Splunk
- Splunk → Correlates and visualizes security events

---

## 🖥 Infrastructure Details
---

| Component | Purpose |
|------------|----------|
| AWS VPC | Isolated enterprise-like cloud network |
| Active Directory | Identity and authentication management |
| Windows Endpoint | Simulated employee workstation |
| Web Server (DVWA) | Vulnerable web application testing |
| Splunk Enterprise | Centralized SIEM platform |
| Universal Forwarder | Log collection agent |
| Kali Linux | Controlled attack simulation |

---

## 🔐 Simulated Attack Scenarios
---

The following controlled attack simulations were performed:

- Brute force login attempts
- Password spray attack
- Privilege escalation
- Unauthorized user creation
- SQL injection testing
- Network reconnaissance (port scanning)

These scenarios helped simulate real-world security threats within a controlled lab environment.

---

## 🧠 Key Learning Outcomes
---

- Built enterprise cloud infrastructure using AWS
- Implemented centralized log monitoring with Splunk
- Understood Active Directory authentication logging
- Correlated endpoint, server, and web logs
- Simulated and analyzed real-world attack scenarios
- Improved understanding of SOC monitoring workflows

---

## 🏆 Project Outcome
---

Successfully developed a fully functional cloud-based SOC lab capable of:

- Monitoring authentication activities
- Detecting suspicious login attempts
- Tracking privilege changes
- Analyzing web traffic activity
- Providing centralized security visibility

## 👤 Author
---

**Nadhil**  
