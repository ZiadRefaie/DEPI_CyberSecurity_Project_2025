# DEPI_CyberSecurity_Project_2025  
## Network Security Fundamentals and FortiGate Integration  

*Project Repository — National Bank (HQ + 4 Branches)*  
![Bankv2](https://github.com/ZiadRefaie/DEPI_CyberSecurity_Project_2025/blob/main/Bankv2.png?raw=true)

---

## 📌 Project Overview  
This project outlines the design and implementation of a **National Bank network infrastructure** using **Cisco networking devices** for routing and switching, integrated with **FortiGate NGFWs** for security, and fully simulated in the **GNS3 environment**.  

The network consists of:  
- **1 Headquarters (HQ)**  
- **4 Branches**  
- All interconnected securely through **WAN links**.

Done Tasks: ✔️
- **Topology Built:** HQ and 4 Branch sites constructed in GNS3. ✔️
- **Cisco Routers Configured:** OSPF routing implemented across all 6 routers for dynamic path selection. ✔️
- **IP Addressing:** Static IPs assigned to all network interfaces. ✔️ (review the Documentation Section for details )
- **Cisco Switches Configured:** ✔️ 
   - VLANs created and trunked for segmentation (Server, User, Management).
   - SVIs are configured on L3 switches for inter-VLAN routing.
   - Access ports assigned for end-hosts.
- **End-Host Connectivity:** Basic layer 2 and layer 3 connectivity established between devices within the same site. ✔️
- **Network Services Configuration:** ✔️
     -  Set up DHCP servers on FortiGates for user VLANs.
     -  Configure necessary NAT policies (Source NAT for internet access).
 -  - **HA Cluster Setup:** Configure the two HQ FortiGates into an Active-Passive High Availability cluster. ✔️   

To be done Tasks:❌

 - **IPsec VPN Establishment:** Build encrypted Site-to-Site VPN tunnels between the HQ and each of the four branches. ❌
 - **Security Policy Creation:** Define and implement zone-based firewall policies to enforce least-privilege access. ❌
 - **Policy Routing & Integration:** Ensure secure traffic flow over the VPN tunnels by integrating FortiGate policies with the existing OSPF routing table. ❌

---

## 🔒 1. The Challenge: Securing a National Bank  

Banks handle highly sensitive customer and financial data, making network design and security a top priority. The main challenges addressed are:  

- **Data Protection:** Ensure confidentiality, integrity, and availability of financial data.  
- **Threat Mitigation:** Defend against malware, ransomware, phishing, and DoS/DDoS attacks.  
- **Secure Connectivity:** Enable secure HQ–Branch and internet communication.  
- **Regulatory Compliance:** Meet PCI DSS and banking data privacy requirements.  
- **High Availability:** Ensure redundancy for uninterrupted banking services.  

---

## 📍 2. Project Scope  

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

## ⚙️ 3. GNS3 Setup & Device List  

### Fortinet Devices  
- **HQ:** 2 × FortiGates (HA).   
- **Total:** **2 FortiGates**.  

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

