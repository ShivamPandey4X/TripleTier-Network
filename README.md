# TripleTier Network Design

## Project Overview
This project involves designing and implementing a robust, scalable network for a trading floor support center with 600 staff members. The new building, identified for expansion, has no existing network infrastructure. The goal is to create a network solution that ensures redundancy, security, and efficient communication across all departments. The network design and implementation will be done using Cisco Packet Tracer.

## Network Design Specifications

### Building Layout
- **First Floor:**
  - Sales and Marketing Department: 120 users
  - Human Resource and Logistics Department: 120 users
- **Second Floor:**
  - Finance and Accounts Department: 120 users
  - Administrator and Public Relations Department: 120 users
- **Third Floor:**
  - ICT Department: 120 users
  - Server Room: 12 devices

### Logical Design

#### Hierarchical Network Model
1. **Core Layer:**
   - Two routers for redundancy
   - Connection to two ISPs for redundancy

2. **Distribution Layer:**
   - Two multilayer switches for redundancy
   - Inter-VLAN routing and core router connectivity

3. **Access Layer:**
   - Switches and wireless access points for end-device connectivity

#### Network Redundancy
- Dual routers connected to two ISPs
- Dual multilayer switches at the distribution layer
- Redundant links between core and distribution layers

#### VLANs and Subnetting
- Each department will be assigned a separate VLAN and subnet.
- Base network: `172.16.1.0/24`

### Subnet Allocation
| Department                           | VLAN | Subnet             | Number of Users |
|--------------------------------------|------|--------------------|-----------------|
| Sales and Marketing                  | 10   | 172.16.10.0/24     | 120             |
| Human Resource and Logistics         | 20   | 172.16.20.0/24     | 120             |
| Finance and Accounts                 | 30   | 172.16.30.0/24     | 120             |
| Administrator and Public Relations   | 40   | 172.16.40.0/24     | 120             |
| ICT                                  | 50   | 172.16.50.0/24     | 120             |
| Server Room                          | 60   | 172.16.60.0/28     | 12              |

### Public IP Address Allocation
- ISP connections: 
  - `195.136.17.0/30`
  - `195.136.17.4/30`
  - `195.136.17.8/30`
  - `195.136.17.12/30`

### Device Configuration
- Hostnames, console passwords, enable passwords, banner messages
- Disabling IP domain lookup
- VLAN assignment and configuration
- Inter-VLAN routing on multilayer switches (Switch Virtual Interfaces)
- DHCP server configuration for dynamic IP allocation
- Static IP allocation for server room devices
- OSPF configuration for route advertisement
- SSH configuration for secure remote login
- Port-security configuration for Finance and Accounts department
- PAT configuration for NAT overload
- Standard and extended ACLs

## Implementation Steps

### Step 1: Network Topology
1. Create a network topology using Cisco Packet Tracer.
2. Connect networking devices with correct cabling.

### Step 2: Basic Device Configuration
1. Configure hostnames, console passwords, enable passwords, and banner messages.
2. Disable IP domain lookup on all devices.

### Step 3: VLAN and IP Addressing
1. Create VLANs and assign ports to VLANs.
2. Subnet the base network `172.16.1.0/24` to allocate IP addresses to each department.

### Step 4: Inter-VLAN Routing
1. Configure Switch Virtual Interfaces (SVIs) on multilayer switches for inter-VLAN routing.
2. Assign IP addresses to SVIs.

### Step 5: DHCP Server Configuration
1. Configure a dedicated DHCP server in the server room.
2. Ensure all devices obtain IP addresses dynamically.

### Step 6: Static IP Configuration
1. Assign static IP addresses to devices in the server room.

### Step 7: Routing Protocol Configuration
1. Configure OSPF on routers and multilayer switches to advertise routes.

### Step 8: Secure Remote Access
1. Configure SSH on all routers and layer three switches.

### Step 9: Port Security
1. Configure port-security for the Finance and Accounts department.
2. Use sticky method to obtain MAC addresses and set violation mode to shutdown.

### Step 10: NAT Overload Configuration
1. Configure PAT using the respective outbound router interface IPv4 address.
2. Implement the necessary ACL rule.

### Step 11: WLAN Configuration
1. Configure wireless networks for each department using Cisco Access Points.

### Step 12: ISP Router Configuration
1. Configure ISP routers with the provided public IP addresses.

### Step 13: Testing and Verification
1. Test network communication and ensure all configurations are working as expected.
2. Verify connectivity, inter-VLAN routing, DHCP operation, OSPF routing, SSH access, port security, and PAT.

## Conclusion
This network design ensures redundancy, scalability, and efficient communication across all departments. The use of Cisco Packet Tracer allows for simulation and verification of the network before actual implementation. By following the hierarchical model and implementing the specified configurations, the network will meet current business needs and be future-proofed for growth!



