# DEPI_CyberSecurity_Project_2025  
## Network Security Fundamentals and FortiGate Integration  

*Project Repository — National Bank (HQ + 4 Branches)*  
![Bank Network Topology](https://github.com/ZiadRefaie/DEPI_CyberSecurity_Project_2025/blob/3b919c2e81d75f5a1548245fd3e3ecf3f348bd97/Bank_Topology.png)

---

## 📌 Project Overview  
This project outlines the design and implementation of a **National Bank network infrastructure** using **Cisco networking devices** for routing and switching, integrated with **FortiGate NGFWs** for security, and fully simulated in the **GNS3 environment**.  

The network consists of:  
- **1 Headquarters (HQ)**  
- **4 Branches**  
- All interconnected securely through **WAN links**.

Done Tasks: ✔️
   Topology Built
To be done Tasks:❎
   Cisco Routers Configured
   Cisco Switches Configured
   IP Addressing
   End-Host Connectivity
   HA Cluster Setup
   IPsec VPN Establishment.
   Security Policy Creation
   Network Services Configuration
   Policy Routing & Integration

---

## 🔒 1. The Challenge: Securing a National Bank  

Banks handle highly sensitive customer and financial data, making network design and security a top priority. The main challenges addressed are:  

- **Data Protection:** Ensure confidentiality, integrity, and availability of financial data.  
- **Threat Mitigation:** Defend against malware, ransomware, phishing, and DoS/DDoS attacks.  
- **Secure Connectivity:** Enable secure HQ–Branch and internet communication.  
- **Regulatory Compliance:** Meet PCI DSS and banking data privacy requirements.  
- **High Availability:** Ensure redundancy for uninterrupted banking services.  

---

## 🛠 2. Solution Approach  

The network combines **Cisco routers & switches** with **FortiGate NGFWs** for advanced security.  
The simulation is fully deployed in **GNS3**, offering flexibility for configuration, testing, and troubleshooting.  

### Key Elements  
- **FortiGate NGFWs** → Firewalling, VPNs, and advanced security at HQ & branches.  
- **Cisco Routers & Switches** → Handle routing, VLAN segmentation, and WAN links.  
- **HQ Redundancy** → Dual routers, dual core switches, and VLAN separation for End Users, Servers, and Management.  
- **WAN Links** → Simulated serial links between HQ and branches.  
- **End Devices** → PCs, printers, ATMs, and servers simulated using VPCS.  

---

## 📍 3. Project Scope  

### Headquarters (HQ)  
- **Routers:** 2 (ISP connectivity & branch links).  
- **Switches:** 2 × L3 Core + 2 × L2 Access.  
- **Servers:** DHCP, AAA, and System Logs.  
- **VLANs:** End Users, Servers, Management.  
- **Security:** 2 × FortiGate NGFWs in HA (Active/Passive).  

### Branches (4 Total)  
- **Routers:** 1 per branch.  
- **Switches:** 1 per branch.  
- **End Devices:** 3–4 PCs/Printers/ATMs per branch.  
- **Security:** 1 × FortiGate NGFW per branch.  

### Connectivity  
- **Internet:** HQ routers connect to ISP (via GNS3 Cloud).  
- **WAN:** Serial links connect HQ with each branch router.  

---

## ⚙️ 4. GNS3 Setup & Device List  

### Fortinet Devices  
- **HQ:** 2 × FortiGates (HA).  
- **Branches:** 1 × FortiGate each (×4).  
- **Total:** **6 FortiGates**.  

### Cisco Devices  
- **Routers:**  
  - HQ = 2  
  - Branches = 4  
  - **Total: 6**  

- **Switches:**  
  - HQ = 4 (2 × L3 + 2 × L2)  
  - Branches = 4 (1 each)  
  - **Total: 8**  

### End Devices (VPCS)  
- **HQ:** ~6 (Users + Servers: DHCP, AAA, Syslogs).  
- **Branches:** ~3–4 per branch.  
- **Total: ~20**  

---

## ✅ Summary  
This project simulates a **realistic bank network** at a CCNA level with **FortiGate NGFW integration** for enterprise security. Using **GNS3**, it demonstrates:  
- Routing & VLAN fundamentals  
- Secure HQ–Branch WAN design
- High availability at HQ  
- Firewall, VPN, and policy enforcement  

## :no_pedestrians: Team Members

| No | Names                             | ID       |
|----|-----------------------------------|----------|
| 1  | Ziad Refaie AbuAlftooh            | 21043261 |
| 2  | Abdullah Ibrahim Abdo             | 21027586 |
| 3  | Mahmoud Mohamed Mahmoud Fahim     | 21080355 |
| 4  | Haitham Ibrahim Mahmoud Hosny     | 21045793 | 
| 5  | Abdullah Muhammad Khalifa         | 21098162 | 
| 6  | Ahmed Mohamed Ahmed               | 21082322 |
| 7  | Abdullah Abdelrehim Hassan        | 21093644 |

Under the Supervision of,
Eng\Elhosien Ahmed & Dr.Hussien Harb

