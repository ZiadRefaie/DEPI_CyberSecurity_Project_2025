## Physical_Topology
# Bank Network Physical Documentation

## Device Inventory

| Site       | Device Type         | Quantity | Hostname               | Model            | Role           |
|------------|---------------------|----------|------------------------|------------------|----------------|
| **HQ**     | FortiGate Firewall  | 2        | FW-HQ1, FW-HQ2         | FortiGate 7.0.9v | HA Cluster     |
| **HQ**     | Cisco Router        | 2        | HQ1_R, HQ2_R           | Cisco 7200       | Core Routing   |
| **HQ**     | Cisco L3 Switch     | 2        | HQ1_MLS, HQ2_MLS       | Cisco 3650       | Core Switching |
| **HQ**     | Cisco L2 Switch     | 2        | HQ1_SW, HQ2_SW         | Cisco 2960       | Access Layer   |
| **Branch 1**| Cisco Router       | 1        | R-BR1                  | Cisco 7200       | Branch Routing |
| **Branch 1**| Cisco Switch       | 1        | SW-BR1                 | Cisco 2960       | Branch Switching|
| **Branch 2**| Cisco Router       | 1        | R-BR2                  | Cisco 7200       | Branch Routing |
| **Branch 2**| Cisco Switch       | 1        | SW-BR2                 | Cisco 2960       | Branch Switching|
| **Branch 3**| Cisco Router       | 1        | R-BR3                  | Cisco 7200       | Branch Routing |
| **Branch 3**| Cisco Switch       | 1        | SW-BR3                 | Cisco 2960       | Branch Switching|
| **Branch 4**| Cisco Router       | 1        | R-BR4                  | Cisco 7200       | Branch Routing |
| **Branch 4**| Cisco Switch       | 1        | SW-BR4                 | Cisco 2960       | Branch Switching|

## 4.0 Physical Connections

| Connection ID | From Device          | From Interface       | To Device            | To Interface         | Cable Type | Speed/Duplex | Purpose                                 | Notes                        |
|---------------|----------------------|----------------------|----------------------|----------------------|------------|--------------|-----------------------------------------|------------------------------|
| PC-HQ-001     | FortiGate-7.0.9-1    | port1                | HQ1 Router           | s1/0                 | Ethernet   | Auto         | Primary WAN Uplink to Internet          | FortiGate External Interface |
| PC-HQ-002     | FortiGate-7.0.9-1    | port2                | HQ-SW-1              | e0/0                 | Ethernet   | Auto         | LAN Uplink to HQ End-Users Switch Stack | Trunk Port                   |
| PC-HQ-003     | FortiGate-7.0.9-2    | port1                | HQ2 Router           | s1/0                 | Ethernet   | Auto         | Secondary WAN Uplink to Internet        | FortiGate External Interface |
| PC-HQ-004     | FortiGate-7.0.9-2    | port2                | HQ-SW-2              | e0/0                 | Ethernet   | Auto         | LAN Uplink to HQ Server Room Switch Stack | Trunk Port                 |
| PC-HQ-005     | FortiGate-7.0.9-1    | e0/1                 | FortiGate-7.0.9-2    | e0/1                 | Ethernet   | Auto         | HA Heartbeat/Sync                       | Dedicated HA Link            |
| PC-HQ-006     | HQ1 Router           | s1/0                 | Branch2 Router       | e0/0                 | Ethernet   | Auto         | WAN Link to Branch 2                    | Point-to-point               |
| PC-HQ-007     | HQ1 Router           | s1/1                 | Branch1 Router       | e0/0                 | Ethernet   | Auto         | WAN Link to Branch 1                    | Point-to-point               |
| PC-HQ-008     | HQ2 Router           | s1/1                 | Branch3 Router       | e0/0                 | Ethernet   | Auto         | WAN Link to Branch 3                    | Point-to-point               |
| PC-HQ-009     | HQ2 Router           | s1/0                 | Branch4 Router       | e0/0                 | Ethernet   | Auto         | WAN Link to Branch 4                    | Point-to-point               |
| PC-HQ-010     | HQ-SW-1              | e0/1                 | PC1 (End-Users)      | N/A                  | Ethernet   | Auto         | IT Staff Workstation                    | Access Port                  |
| PC-HQ-011     | HQ-SW-1              | e0/2                 | PC2 (End-Users)      | N/A                  | Ethernet   | Auto         | Sales Department Workstation            | Access Port                  |
| PC-HQ-012     | HQ-SW-1              | e0/3                 | PC3 (End-Users)      | N/A                  | Ethernet   | Auto         | ATM Simulator PC                        | Access Port                  |
| PC-HQ-013     | HQ-SW-2              | e0/0                 | AAA Server           | N/A                  | Ethernet   | Auto         | Authentication Server                   | Access Port                  |
| PC-HQ-014     | HQ-SW-2              | e1/0                 | Syslog Server        | N/A                  | Ethernet   | Auto         | Logging Server                          | Access Port                  |
| PC-HQ-015     | HQ-SW-2              | e2/0                 | DHCP Server          | N/A                  | Ethernet   | Auto         | IP Management Server                    | Access Port                  |
| PC-BR1-001    | Branch1 Router       | e1/0                 | BR1-SW-1             | e0/0                 | Ethernet   | Auto         | LAN Uplink to Branch 1 Access Switch    | Trunk Port                   |
| PC-BR1-002    | BR1-SW-1             | e0/1                 | PC1 (Branch 1)       | N/A                  | Ethernet   | Auto         | Teller Workstation                      | Access Port                  |
| PC-BR1-003    | BR1-SW-1             | e0/2                 | PC2 (Branch 1)       | N/A                  | Ethernet   | Auto         | Customer Service PC                     | Access Port                  |
| PC-BR1-004    | BR1-SW-1             | e0/3                 | PC3 (Branch 1)       | N/A                  | Ethernet   | Auto         | ATM Simulator                           | Access Port                  |
| PC-BR2-001    | Branch2 Router       | e1/0                 | BR2-SW-1             | e0/0                 | Ethernet   | Auto         | LAN Uplink to Branch 2 Access Switch    | Trunk Port                   |
| PC-BR2-002    | BR2-SW-1             | e0/1                 | PC1 (Branch 2)       | N/A                  | Ethernet   | Auto         | Teller Workstation                      | Access Port                  |
| PC-BR2-003    | BR2-SW-1             | e0/2                 | PC2 (Branch 2)       | N/A                  | Ethernet   | Auto         | Customer Service PC                     | Access Port                  |
| PC-BR2-004    | BR2-SW-1             | e0/3                 | PC3 (Branch 2)       | N/A                  | Ethernet   | Auto         | ATM Simulator                           | Access Port                  |
| PC-BR3-001    | Branch3 Router       | e1/0                 | BR3-SW-1             | e0/0                 | Ethernet   | Auto         | LAN Uplink to Branch 3 Access Switch    | Trunk Port                   |
| PC-BR3-002    | BR3-SW-1             | e0/1                 | PC1 (Branch 3)       | N/A                  | Ethernet   | Auto         | Teller Workstation                      | Access Port                  |
| PC-BR3-003    | BR3-SW-1             | e0/2                 | PC2 (Branch 3)       | N/A                  | Ethernet   | Auto         | Customer Service PC                     | Access Port                  |
| PC-BR3-004    | BR3-SW-1             | e0/3                 | PC3 (Branch 3)       | N/A                  | Ethernet   | Auto         | ATM Simulator                           | Access Port                  |
| PC-BR4-001    | Branch4 Router       | e1/0                 | BR4-SW-1             | e0/0                 | Ethernet   | Auto         | LAN Uplink to Branch 4 Access Switch    | Trunk Port                   |
| PC-BR4-002    | BR4-SW-1             | e0/1                 | PC1 (Branch 4)       | N/A                  | Ethernet   | Auto         | Teller Workstation                      | Access Port                  |
| PC-BR4-003    | BR4-SW-1             | e0/2                 | PC2 (Branch 4)       | N/A                  | Ethernet   | Auto         | Customer Service PC                     | Access Port                  |
| PC-BR4-004    | BR4-SW-1             | e0/3                 | PC3 (Branch 4)       | N/A                  | Ethernet   | Auto         | ATM Simulator                           | Access Port                  |

## IP Addressing Scheme

## HQ Subnets

| Subnet Name | Network CIDR  | Gateway      | VLAN ID | Purpose                  | Interface |
|-------------|---------------|--------------|---------|--------------------------|-----------|
| SERVERS     | 10.100.0.0/24 | 10.100.0.1   | 10      | Core Banking Servers     | N/A       |
| USERS       | 10.5.10.0/24  | 10.5.10.1    | 20      | HQ Staff Workstations    | E0/1      |
| Servers     | 172.16.10.0/24| 172.16.10.1  | 200     | DHCP, AAA Servers        | E0/1, E0/2|
| IT          | 10.5.10.0/24  | 10.5.10.1    | 10      | IT Staff                 | E0/1      |
| Sales       | 10.5.20.0/24  | 10.5.20.1    | 20      | Sales Department         | E0/2      |
| ATM         | 10.5.30.0/24  | 10.5.30.1    | 30      | ATM Services             | E0/3      |
| Voice       | 10.5.40.0/24  | 10.5.40.1    | 40      | Voice Services           | E1/0      |
| Native      | 10.5.0.0/24   | 10.5.0.1     | 99      | Native VLAN              | N/A       |
| Management  | 10.5.100.0/24 | 10.5.100.1   | 100     | Network Device Management| N/A       |

## Branch Subnets

### Branch 1 (BR1)

| Subnet Name | Network CIDR  | Gateway      | VLAN ID | Purpose                  | Interface |
|-------------|---------------|--------------|---------|--------------------------|-----------|
| IT          | 10.1.10.0/24  | 10.1.10.1    | 10      | IT Staff                 | E0/1      |
| Sales       | 10.1.20.0/24  | 10.1.20.1    | 20      | Sales Department         | E0/2      |
| ATM         | 10.1.30.0/24  | 10.1.30.1    | 30      | ATM Services             | E0/3      |
| Voice       | 10.1.40.0/24  | 10.1.40.1    | 40      | Voice Services           | E1/0      |
| Native      | N/A           | N/A          | 99      | Native VLAN              | N/A       |
| Management  | 10.1.100.0/24 | 10.1.100.1   | 100     | Network Device Management| N/A       |

### Branch 2 (BR2)

| Subnet Name | Network CIDR  | Gateway      | VLAN ID | Purpose                  | Interface |
|-------------|---------------|--------------|---------|--------------------------|-----------|
| IT          | 10.2.10.0/24  | 10.2.10.1    | 10      | IT Staff                 | E0/1      |
| Sales       | 10.2.20.0/24  | 10.2.20.1    | 20      | Sales Department         | E0/2      |
| ATM         | 10.2.30.0/24  | 10.2.30.1    | 30      | ATM Services             | E0/3      |
| Voice       | 10.2.40.0/24  | 10.2.40.1    | 40      | Voice Services           | E1/0      |
| Native      | N/A           | N/A          | 99      | Native VLAN              | N/A       |
| Management  | 10.2.100.0/24 | 10.2.100.1   | 100     | Network Device Management| N/A       |

### Branch 3 (BR3)

| Subnet Name | Network CIDR  | Gateway      | VLAN ID | Purpose                  | Interface |
|-------------|---------------|--------------|---------|--------------------------|-----------|
| IT          | 10.3.10.0/24  | 10.3.10.1    | 10      | IT Staff                 | E0/1      |
| Sales       | 10.3.20.0/24  | 10.3.20.1    | 20      | Sales Department         | E0/2      |
| ATM         | 10.3.30.0/24  | 10.3.30.1    | 30      | ATM Services             | E0/3      |
| Voice       | 10.3.40.0/24  | 10.3.40.1    | 40      | Voice Services           | E1/0      |
| Native      | N/A           | N/A          | 99      | Native VLAN              | N/A       |
| Management  | 10.3.100.0/24 | 10.3.100.1   | 100     | Network Device Management| N/A       |

### Branch 4 (BR4)

| Subnet Name | Network CIDR  | Gateway      | VLAN ID | Purpose                  | Interface |
|-------------|---------------|--------------|---------|--------------------------|-----------|
| IT          | 10.4.10.0/24  | 10.4.10.1    | 10      | IT Staff                 | E0/1      |
| Sales       | 10.4.20.0/24  | 10.4.20.1    | 20      | Sales Department         | E0/2      |
| ATM         | 10.4.30.0/24  | 10.4.30.1    | 30      | ATM Services             | E0/3      |
| Voice       | 10.4.40.0/24  | 10.4.40.1    | 40      | Voice Services           | E1/0      |
| Native      | N/A           | N/A          | 99      | Native VLAN              | N/A       |
| Management  | 10.4.100.0/24 | 10.4.100.1   | 100     | Network Device Management| N/A       |

## End Devices (VPCS)

| Site         | Quantity | Device Type           | IP Range                   | Purpose             |
|--------------|----------|-----------------------|----------------------------|---------------------|
| **HQ**       | 1        | DHCP Server           | 172.16.10.10               | IP Management       |
| **HQ**       | 1        | AAA Server            | 172.16.10.20               | Authentication      |
| **HQ**       | 1        | Syslog Server         | 172.16.10.30               | Logging             |
| **Each Branch**| 2      | Teller Workstations   | 10.1.10.100-150            | Banking Operations  |
| **Each Branch**| 1      | Customer Service PC   | 10.1.10.151-160            | Customer Support    |
| **Each Branch**| 1      | ATM Simulator         | 10.1.10.161-170            | ATM Interface       |

## Total Device Summary

| Device Type          | HQ Count | Branch Count | Total |
|----------------------|----------|--------------|-------|
| FortiGate Firewalls  | 2        | 0            | 2     |
| Cisco Routers        | 2        | 4            | 6     |
| Cisco Switches       | 4        | 4            | 8     |
| End Devices (VPCS)   | 6        | 16           | 22    |
| **GRAND TOTAL**      | **14**   | **28**       | **42**|

---
**Project:** Bank Network Security & FortiGate Integration  
**Topology:** 1 HQ + 4 Branches


