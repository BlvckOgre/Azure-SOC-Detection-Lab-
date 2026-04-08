# Azure SOC Detection Lab  
**Multi-Domain Detection Engineering using YARA, Sigma, Snort & Microsoft Sentinel**

---

##  **Project Overview**

This project is a full-scale **Azure-based Security Operations Center (SOC) lab** designed to simulate a real-world enterprise environment under attack.

It integrates detection across three domains:

- **Network Detection** → Snort / Suricata + Wireshark  
- **Log Detection** → Sigma-style detections implemented in Microsoft Sentinel (KQL)  
- **File Detection** → YARA rules for malware and suspicious file scanning  

The lab includes:
- Simulated enterprise network (user, DMZ, attacker zones)
- Real attack simulation via Kali Linux
- Centralized monitoring via Microsoft Sentinel
- Detection correlation across network, endpoint, and file layers

---

## Architecture Overview

The environment is deployed in Azure using a segmented network architecture:

### Core Components

| Zone | Description |
|------|------------|
| Management / SOC | Microsoft Sentinel, Log Analytics, Storage |
| User Network | Windows + Linux endpoints |
| DMZ Network | Vulnerable web application (DVWA / Juice Shop) |
| Sensor Network | Snort / Suricata IDS + packet capture |
| Attacker Network | Kali Linux attack machine |

### Key Technologies

- Azure Virtual Network (VNet)
- Network Security Groups (NSGs)
- Microsoft Sentinel (SIEM)
- Log Analytics Workspace
- Sysmon & Linux logging
- Snort / Suricata IDS
- Wireshark / tcpdump
- YARA (file scanning)

---

## 🎯 Objectives

- Simulate real-world cyber attacks
- Build detection rules across multiple domains
- Correlate alerts in a SIEM (Sentinel)
- Practice SOC investigation workflows
- Develop detection engineering skills

---

##  Project Setup (Step-by-Step)

---

###  Phase 1: Azure Infrastructure Setup

1. Create Resource Group
2. Create Virtual Network (VNet)
3. Create Subnets:
   - Management
   - User
   - DMZ
   - Sensor
   - Attacker

4. Configure Network Security Groups (NSGs)
5. Deploy Log Analytics Workspace
6. Enable Microsoft Sentinel
7. Create Storage Account

---

###  Phase 2: Deploy Virtual Machines

Deploy the following:

- Windows 10/11 VM (User)
- Linux VM (User)
- Linux Web Server (DMZ)
- Snort/Suricata Sensor VM
- Kali Linux VM (Attacker)

Optional:
- Jumpbox (Management)
- pfSense Firewall (for advanced segmentation)

---

###  Phase 3: Endpoint Instrumentation

#### Windows
- Install Sysmon
- Enable:
  - PowerShell logging
  - Process auditing
- Install Azure Monitor Agent

#### Linux
- Install:
  - auditd
  - syslog forwarding
  - Azure Monitor Agent
  - YARA

---

###  Phase 4: Network Monitoring Setup

- Install Snort or Suricata on Sensor VM
- Configure rules for:
  - Port scanning
  - Brute force attempts
  - Suspicious HTTP traffic

- Capture traffic using:
  - tcpdump
  - Wireshark

---

###  Phase 5: File Detection (YARA)

- Install YARA on endpoints
- Create rules to detect:
  - Suspicious scripts
  - Known malware patterns
  - Encoded payloads

- Automate scanning:
  - Cron jobs (Linux)
  - Scheduled tasks (Windows)

- Send YARA results to Sentinel

---

###  Phase 6: Log Detection (Sigma → Sentinel)

- Write Sigma-style detection logic for:
  - Failed logins
  - Suspicious PowerShell usage
  - Process anomalies

- Translate into KQL queries in Sentinel
- Create analytics rules

---

###  Phase 7: Attack Simulation

Using Kali Linux:

- Nmap scanning
- Brute force attacks
- Web exploitation
- File uploads (malicious samples)
- PowerShell payload execution

---

###  Phase 8: Detection & Correlation

- Monitor alerts in Sentinel
- Correlate:
  - Network alerts (Snort)
  - Log alerts (KQL)
  - File detections (YARA)

---

##  Detection Use Cases

| Scenario | Detection Type |
|--------|--------------|
| Port scanning | Snort / Suricata |
| Brute-force login | Sigma → KQL |
| Malicious file upload | YARA |
| PowerShell abuse | Sigma → KQL |
| Web exploitation | Snort + Logs |

---

##  Investigation (TO BE COMPLETED)

> This section will be updated after full attack simulations are conducted.

### Planned Analysis

- Incident timeline reconstruction
- Detection effectiveness review
- False positive analysis
- Correlation between domains
- Gaps in visibility

---

##  Future Improvements

- Add automated response (Logic Apps)
- Integrate Defender for Endpoint
- Add threat intelligence feeds
- Expand attack scenarios
- Implement SOAR workflows

---

##  Repository Structure






---

##  Skills Demonstrated

- Cloud Security Architecture (Azure)
- Detection Engineering
- SIEM Implementation (Sentinel)
- Network Security Monitoring
- Endpoint Telemetry Analysis
- Threat Simulation & Analysis

---

##  Author

Dimakatso Malope  
Data Engineer | Cybersecurity Analyst  

---
