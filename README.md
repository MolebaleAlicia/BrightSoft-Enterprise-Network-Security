# BrightSoft Solutions - Enterprise Network Security Infrastructure

A simulated multi-floor corporate network infrastructure designed and configured in Cisco Packet Tracer (NQF Level 6 project). The network supports three operational floors with logical segmentation, inter-departmental security controls, and high-availability routing.

## Network Architecture Overview
* **Address Space:** `192.168.0.0/24`
* **Floor 1 (Devs & Business Analysts):** Dedicated subnets with local DHCP servers, connected via legacy **RIPv2** routing.
* **Floor 2 (Test Engineers & UI Designers):** Logical separation using **802.1Q VLAN trunking** on a Layer 3 switch, routed via **OSPF**.
* **Floor 3 (Staging Environment):** DMZ-style staging server accessible externally for client demos via HTTP/HTTPS while restricting internal lateral movement.
* **Central Infrastructure:** Central DNS (`192.168.0.13`), Production Web Server (`192.168.0.14`), and Syslog logging (`192.168.0.15`).

## Security & Routing Highlights
* **Access Control Lists (ACLs):** Configured extended ACLs on edge and shared routers to block direct traffic between Test Engineers and UI Designers while permitting controlled access to shared resources.
* **DMZ & NAT/Port Forwarding:** Implemented Network Address Translation (NAT) and strict firewall/ACL rules to allow approved external partner access to the staging server without exposing internal networks.
* **Dynamic Routing & Redundancy:** Hybrid routing strategy employing RIPv2 and OSPF with mutual route redistribution and a backup link between the Shared Router and Business Analysts Router for failover resilience.

## How to Test & Verify
1. Download and install **Cisco Packet Tracer** (v8.x or higher).
2. Download `BrightSoft-Enterprise-Network-Security (2).pkt` from this repository.
3. Open the file to inspect running configurations or execute ping/HTTP simulation tests across subnets.
