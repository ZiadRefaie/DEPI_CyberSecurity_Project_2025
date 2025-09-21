# DEPI_CyberSecurity_Project_2025  
## Network Security Fundamentals and FortiGate Integration  

| No | Names                             | ID       |
|----|-----------------------------------|----------|
| 1  | Ziad Refaie AbuAlftooh            | 21043261 |
| 2  | Abdullah Ibrahim Abdo             | 21027586 |
| 3  | Mahmoud Mohamed Mahmoud Fahim     | 21080355 |
| 4  | Haitham Ibrahim Mahmoud Hosny     | 21045793 |
| 5  | Abdullah Muhammad Khalifa         | 21098162 |
| 6  | Ahmed Mohamed Ahmed               | 21082322 |
| 7  |                                   |          |


# Building a Secure National Bank Network with FortiGate & Cisco (GNS3 Project)

## Project Overview

Welcome to the **Network Security Fundamentals and FortiGate Integration** project repository! This document outlines our ambitious journey to design, implement, and secure a robust network infrastructure for a hypothetical National Bank. Our core objective is to leverage industry-leading FortiGate Next-Generation Firewalls (NGFWs) for comprehensive security, seamlessly integrated with Cisco networking devices for routing and switching, all within the powerful GNS3 simulation environment.

This project aims to serve as a practical demonstration of advanced network security concepts, diverse FortiGate capabilities (including SD-WAN, VPN, and Security Fabric), and best practices for fortifying critical financial institutions against modern cyber threats.

## 1. The Challenge: Securing a National Bank

A national bank operates across multiple geographically distributed locations, handling a vast volume of sensitive financial transactions and invaluable customer data. This critical environment necessitates a network infrastructure that is not only highly available, scalable, and efficient but also rigorously fortified against an ever-evolving landscape of cyber threats. Key security challenges inherent to this sector include:

*   **Data Protection:** Rigorously safeguarding customer accounts, transaction histories, personal identifiable information (PII), and internal financial records from unauthorized access, modification, or disclosure.
*   **Regulatory Compliance:** Strict adherence to a multitude of financial industry regulations and standards (e.g., PCI DSS for payment card data, GDPR/local data privacy laws, principles derived from ISO 27001 for information security management).
*   **Threat Mitigation:** Implementing proactive and reactive measures to protect against malware, ransomware, phishing attacks, denial-of-service (DoS) and distributed denial-of-service (DDoS) attacks, sophisticated advanced persistent threats (APTs), and internal insider threats.
*   **Secure & Reliable Connectivity:** Ensuring encrypted and reliable communication channels between the Head Office, numerous branch offices, mobile banking platforms, and remote employees.
*   **Business Continuity & Disaster Recovery:** Designing the network with inherent redundancy and failover mechanisms to maintain uninterrupted banking services, even in the event of hardware failures or regional disasters.

## 2. Our Solution Approach

Our project is engineered to address these complex challenges through a multi-layered security architecture, strategically combining the strengths of Fortinet and Cisco technologies:

*   **FortiGate Next-Generation Firewalls (NGFWs):** These will be the cornerstone of our security posture, deployed as the primary perimeter defense at the Head Office and each branch. They will provide advanced threat protection (Intrusion Prevention System - IPS, Antivirus/Anti-Malware, Web Filtering, Application Control), secure VPN connectivity, and potentially advanced SD-WAN capabilities for optimized branch connectivity.
*   **Cisco Routers & Switches:** These will form the robust backbone of our network, providing essential routing and switching functionalities. This includes efficient traffic forwarding, logical network segmentation through VLANs, and Quality of Service (QoS) mechanisms to prioritize critical banking applications.
*   **GNS3 Simulation Environment:** This powerful network emulation platform allows us to build, configure, test, and troubleshoot the entire network infrastructure virtually. This eliminates the need for expensive physical hardware, fostering an agile development process, enabling extensive experimentation, and facilitating easy rollback of changes.
*   **Fortinet Security Fabric Integration:** We will explore how various Fortinet components can seamlessly integrate to form a cohesive security ecosystem. This may include integrating FortiGates with FortiAnalyzer for centralized logging, reporting, and security event analysis, and considering FortiClient for endpoint security awareness.

## 3. Project Scope: The National Bank's Structure

To establish a realistic yet manageable scope for our project, the National Bank's network infrastructure will be designed around the following key organizational structure:

*   **One (1) Head Office (HO):** This will serve as the central operational hub, hosting core banking applications, a primary data center, and all critical back-office functions. The HO will feature the most complex network design, including redundant internet uplinks and a High Availability (HA) cluster of FortiGates.
*   **Seven (7) Branch Offices:** These will be geographically distributed entities, each representing a typical bank branch with local staff networks, ATM kiosks, and client-facing service areas. Each branch will establish secure VPN tunnels back to the Head Office.
*   **Internet Connectivity:** Secured and controlled access to the public internet will be provided for online banking services, employee web access, and various cloud-based banking applications.
*   **Remote Access:** A robust and secure Virtual Private Network (VPN) solution (e.g., SSL VPN) will be implemented to allow authorized bank employees to securely access internal resources while working remotely.

## 4. GNS3 Setup & Initial Device List

Our entire network will be meticulously built and simulated within the GNS3 environment. Below is a breakdown of the initial virtual devices required for the project:

### Fortinet Devices (VM Images):

*   **FortiGate (FortiOS):**
    *   `FortiGate-VM64` (or compatible VM image for GNS3)
    *   *Quantity:* **2** for the Head Office (configured in HA-Active/Passive) + **1** for each of the 7 branches = **9 FortiGates** in total.
    *   *Purpose:* Perimeter security, inter-site VPN tunnels, advanced threat protection, SD-WAN functions.
*   **FortiAnalyzer (Optional but Highly Recommended):**
    *   `FortiAnalyzer-VM64` (or compatible VM image for GNS3)
    *   *Quantity:* **1** (centrally deployed at the Head Office).
    *   *Purpose:* Centralized logging, comprehensive reporting, security event analysis, and compliance auditing.

### Cisco Devices (IOSv Images):

*   **Cisco IOSv (Layer 3 Router):**
    *   `Cisco IOSv L3` (`C7200` ).
    *   *Quantity:* At least **2-4** for the Head Office (for ISP simulation, core routing, DMZ routing) + **1** for each of the 7 branches (for internal branch routing and VLAN routing) = **9-11 Routers** in total.
    *   *Purpose:* Internal routing within HO and branches, simulating ISP connections, potentially running routing protocols like OSPF/EIGRP within the core.
*   **Cisco IOSvL2 (Layer 2 Switch):**
    *   `Cisco IOSv L2` (`3725`).
    *   *Quantity:* At least **2-4** for the Head Office (for core switching, server farm access) + **1** for each of the 7 branches (for access layer switching for employee PCs and ATMs) = **9-11 Switches** in total.
    *   *Purpose:* VLAN segmentation, access layer connectivity, spanning-tree protocol.

### Other GNS3 Elements:

*   **Cloud Node:** Utilized to simulate the external internet, allowing our virtual network to connect to the host machine's physical network and the real internet (if configured).
*   **VPCS (Virtual PC Simulator) / End Hosts:**
    *   *Quantity:* Multiple instances to simulate various network endpoints.
    *   *Purpose:* Represent employee workstations, core banking servers, public-facing web servers (in DMZ), and ATM machines for testing connectivity, security policies, and application access from different segments.

## 5. Initial Steps & Project Phases

To ensure a structured and efficient project workflow, we will follow these key phases:

1.  **GNS3 Environment Setup:** All team members must ensure their GNS3 installations are complete, configured correctly, and that all necessary FortiGate and Cisco IOSv images are imported, licensed (if applicable), and running without issues.
2.  **High-Level Design (HLD):** Develop detailed logical and physical network diagrams for the Head Office and a typical branch. This includes outlining the chosen IP addressing scheme, VLAN segregation, and strategic device placements.
3.  **IP Addressing Plan:** Create a comprehensive, hierarchical IP addressing scheme that logically segments all network zones, subnets, and devices across the entire bank infrastructure.
4.  **Head Office Core Build:** Begin with the foundational configuration of the core Cisco routers and switches at the Head Office, establishing basic internal connectivity and implementing VLANs.
5.  **FortiGate Integration (HO):** Deploy and configure the FortiGate HA cluster at the Head Office. This will involve setting up Internet Edge Security, DMZ protection, and initial firewall policies.
6.  **Branch Office Template Development:** Create a standardized and repeatable configuration template for a single branch office. This includes its Cisco access devices and the branch FortiGate, which can then be replicated across all 7 branches.
7.  **VPN Connectivity Implementation:** Establish secure IPsec VPN tunnels between the Head Office FortiGates and each individual branch FortiGate, ensuring secure inter-site communication. Explore SD-WAN overlays for optimized traffic flow.
8.  **Security Policy & Threat Protection:** Configure granular firewall policies, enable Intrusion Prevention System (IPS), Application Control, Web Filtering, and Antivirus profiles on all FortiGates to enforce robust security.
9.  **FortiAnalyzer Integration:** Integrate all deployed FortiGates with the central FortiAnalyzer instance for aggregated logging, real-time monitoring, and in-depth security analysis.
10. **Testing & Validation:** Conduct rigorous testing of all connectivity paths, security policies (positive and negative testing), VPN tunnels, failover mechanisms (for HO HA pair), and overall network resilience.

## 6. Expected Outcomes & Learning

Through the successful completion of this project, our team expects to gain invaluable hands-on experience and cultivate a deeper, practical understanding of:

*   Enterprise-grade network design principles and best practices for large-scale, distributed environments.
*   Advanced FortiGate firewall configurations, including FortiOS features such as NGFW, VPN, SD-WAN, and Security Fabric.
*   Proficiency in Cisco routing and switching configurations within a multi-VLAN, multi-protocol environment.
*   The implementation of secure VPN topologies, encompassing both Site-to-Site and Remote Access solutions.
*   Fundamental SD-WAN concepts and their practical configuration for improved network performance and cost efficiency.
*   Comprehensive security best practices specifically tailored for critical financial institutions.
*   Advanced troubleshooting methodologies for complex network and security issues within the GNS3 simulation environment.
*   Collaborative project management, documentation, and version control within a team setting.

---
Here's a conceptual diagram of the GNS3 topology, showing the main components and their interconnections:
