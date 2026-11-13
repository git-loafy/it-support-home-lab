# Project 001: Small Office Network Setup

## Objective
Design and configure a simulated small office network that allows multiple client devices, a server, and a network printer to communicate through a central Ethernet switch and router.

## Environment
- Network simulator: NetLab
- 1 Router
- 1 Ethernet switch
- 3 Client computers
- 1 Server
- 1 Network printer

## Network Configuration
- Network: 192.168.10.0/24
- Subnet mask: 255.255.255.0
- Default gateway: 192.168.10.1
- Addressing method: Static IPv4 configuration

## Implementation
- Created a logical network topology.
- Connected client devices and network resources to a central switch.
- Configured the router's LAN interface.
- Assigned static IPv4 addresses to network devices.
- Configured default gateway settings.

## Testing and Verification
- Verified IP configurations using `ipconfig`.
- Tested connectivity between PC 1, the default gateway, other workstations, the server, and network printer using `ping`.
- Inspected router interface addresses and operational status using `show ip interface brief`.
- Verified switch interface connectivity and operational status using `show interfaces`.
- Confirmed that all six connected devices had operational Ethernet links through the central switch.

## Troubleshooting
- Identified an incorrect default gateway configuration preventing PC 1 from communicating with the router.
- Corrected the gateway address from 192.168.1.1 to 192.168.10.1.
- Retested connectivity and confirmed successful communication with the router with 0% packet loss.

## Skills Practiced
- IPv4 addressing
- Subnet masks
- Default gateways
- Ethernet switching
- Router interface configuration
- Static IP configuration
- Network connectivity testing
- Basic network troubleshooting

## Evidence
See the attached network topology and configuration notes.

*This is an independently completed educational simulation, not professional work experience.*
