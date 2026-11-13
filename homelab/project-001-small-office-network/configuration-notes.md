# Project 001 – Configuration Notes

## 1. Network Topology

The simulated network uses a centralized Ethernet switch connected to a router, three client workstations, a network server, and a network printer.

*Figure 1: Simulated small office network topology.*
<img width="1000" height="1125" alt="IMG_7708" src="https://github.com/user-attachments/assets/971eec36-4375-4809-a5f5-f69cce4f8124" />


### Network Devices

- 1 Cisco ISR4331 Router
- 1 3300-24TS Ethernet Switch
- 3 Client Computers (PC, PC2, PC3)
- 1 Server
- 1 Network Printer

## 2. Network Configuration

The network uses an IPv4 private addressing scheme within the `192.168.10.0/24` subnet.

### IP Addressing Scheme

| Device | IPv4 Address |
|---|---|
| Router (Default Gateway) | 192.168.10.1 |
| Server | 192.168.10.10 |
| Network Printer | 192.168.10.20 |
| PC 1 | 192.168.10.101 |
| PC 2 | 192.168.10.102 |
| PC 3 | 192.168.10.103 |

**Subnet Mask:** 255.255.255.0

**Default Gateway:** 192.168.10.1

### PC 1 IP Configuration

Used the `ipconfig` command to inspect PC 1's network configuration.

Verified the following:
- IPv4 Address: 192.168.10.101
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.10.1

*Figure 2: PC IPv4 configuration using ipconfig.* 
<img width="2732" height="1568" alt="IMG_7715" src="https://github.com/user-attachments/assets/d3dd4ad1-8e06-409a-a59f-2096e04d8a45" />


## 3. Implementation, Testing and Verification

Connectivity was tested using the `ping` command to verify communication between network devices.

### Connectivity Testing Results

| Source | Destination | Result |
|---|---|---|
| PC 1 | Router | Successful |
| PC 1 | PC 2 | Successful |
| PC 1 | PC 3 | Successful |
| PC 1 | Server | Successful |
| PC 1 | Network Printer | Successful |
| Network Printer | Server | Successful |
| Server | Network Printer | Successful |

### Ping Test Results

All seven confirmed tests returned:
- Packets Sent: 4
- Packets Received: 4
- Packet Loss: 0%
- Average Response Time: 2 ms

The tests confirmed IP connectivity between PC 1 and its gateway, other workstations, server, and printer, as well as between the printer and server.

### Testing Evidence
*Figure 3 and 4: Successful connectivity between network devices.* 
<img width="2730" height="1038" alt="Bazaart_2026-11-12_175826" src="https://github.com/user-attachments/assets/0cb35a7a-499b-4870-8257-b61f030a1344" />
<img width="2730" height="1565" alt="Bazaart_2026-11-12_175957" src="https://github.com/user-attachments/assets/7c04f2e4-1f7e-4a56-b701-8857b27f2591" />


## 4. Router Interface Verification

Used the `show ip interface brief` command on the Cisco ISR4331 router to inspect interface addresses and operational status.

### Results

| Interface | IP Address | Status | Protocol |
|---|---|---|---|
| GigabitEthernet0/0/0 | 192.168.10.1 | UP | UP |
| GigabitEthernet0/0/1 | Unassigned | DOWN | DOWN |
| GigabitEthernet0/0/2 | Unassigned | DOWN | DOWN |

**Verification:** Confirmed that the router's primary LAN interface is operational and configured with the expected default gateway address. Unused interfaces remain unassigned and inactive.

**Command Used:**
`show ip interface brief`

*Figure 5: Router interface status and IP address assignments displayed.*
<img width="1356" height="1556" alt="IMG_7725" src="https://github.com/user-attachments/assets/c81b5eb3-7111-449a-8ab5-c8bf158bb67b" />


## 5. Switch Interface Verification

Used the `show interfaces` command on the 3300-24TS Ethernet switch to inspect interface status and connectivity.

### Results

- First six connected Ethernet interfaces: UP, line protocol UP.
- Remaining Ethernet interfaces: DOWN, line protocol DOWN.
- Six active connections correspond to the router, three client computers, server, and network printer.

**Verification:** Confirmed that all six connected devices have operational Ethernet links through the central switch. Unused ports remain inactive.

**Command Used:**
`show interfaces`

*Figure 6: Ethernet switch interface status displaying operational and inactive ports.*
<img width="1356" height="1655" alt="IMG_7727" src="https://github.com/user-attachments/assets/511b21e4-827f-4831-8785-fe169b4e38b7" />


## 6. Troubleshooting

During initial configuration, PC 1 was unable to communicate with its default gateway.

The issue was traced to an incorrect default gateway address.

- Initial gateway address: 192.168.1.1
- Corrected gateway address: 192.168.10.1

The original gateway address did not match the configured `192.168.10.0/24` network.

After correcting the gateway address, PC 1 successfully received four replies from `192.168.10.1`, with 0% packet loss.

**Resolution:** Corrected the default gateway configuration to match the router's LAN interface address.

## 7. Skills Practiced

- Small office network topology design
- IPv4 addressing and subnet mask configuration
- Default gateway configuration
- Ethernet switching and wired network connections
- Network device connectivity testing
- Command-line interface (CLI) navigation
- Using `ipconfig` to inspect network configurations
- Using `ping` to verify connectivity
- Interpreting packet loss and response times
- Inspecting router interface status
- Inspecting switch interface status
- Basic network troubleshooting
- Technical documentation and evidence collection
