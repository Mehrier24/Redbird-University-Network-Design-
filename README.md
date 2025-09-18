Redbird University - Secure Enterprise Network Architecture
This project is a comprehensive simulation of a secure enterprise network for a hypothetical university, "Redbird University." Built entirely within Cisco Packet Tracer, this project demonstrates a robust, multi-layered security architecture designed to protect internal assets while providing necessary services.

The primary goal of this project is to showcase practical skills in network design, implementation, and security hardening, covering concepts from Layer 2 security to perimeter defense with a multi-zone firewall.

🌐 Network Topology
The network is comprised of three primary security zones managed by a Cisco ASA Firewall: a trusted inside zone for internal users, a public outside zone simulating the internet, and a secure dmz (Demilitarized Zone) for the university's public-facing web and DNS server. Internal users are further segmented by department using VLANs.

<img width="1729" height="828" alt="Toplogy" src="https://github.com/user-attachments/assets/c62e8a36-a943-4ebd-b17a-c29cf7c4685e" />




🚀 Core Features
This network simulation includes the following key features:

Hierarchical Network Design: A two-tier model with a Layer 3 switch acting as the Core/Distribution layer for high-speed internal routing.

VLAN Segmentation: The internal network is segmented into multiple VLANs (Faculty, Students, Administration) to isolate traffic and enforce security policies.

Secure DMZ Architecture: A multi-zone ASA firewall creates a secure DMZ, isolating the public web server from both the internet and the trusted internal network.

Advanced Firewalling & ACLs: The Cisco ASA 5506-X is configured with strict access control lists (ACLs) to block unauthorized inter-VLAN communication and permit only necessary traffic (HTTP/HTTPS/DNS) into the DMZ from the internet.

Routing & NAT: The network correctly routes traffic between all internal VLANs and the DMZ. Port Address Translation (PAT) allows all internal users to access the internet, and Static NAT (Port Forwarding) securely exposes web services.

Centralized Services: The design includes a centralized DHCP server for dynamic IP allocation and a DNS server for name resolution.

✅ Verification & Testing
The network's functionality and security policies have been rigorously tested. The following screenshots serve as evidence of a successful implementation.

1. DHCP IP Assignment
End-user devices successfully receive their IP address, subnet mask, default gateway, and DNS server information from the DHCP server configured on the Core Switch.

<img width="697" height="331" alt="Dhcp Success" src="https://github.com/user-attachments/assets/1551a8c1-30ef-4f07-b85e-535feaa6e5eb" />

2. Internal Connectivity
Internal devices can successfully communicate with their default gateway and other required network resources, such as the web server in the DMZ.

Faculty PC Pinging its Gateway (10.10.10.1):

<img width="679" height="387" alt="Faculty PC pinging Gateway" src="https://github.com/user-attachments/assets/b9ea5487-f2fa-462a-be70-af6d7609f41f" />

Faculty PC Pinging the Web Server (172.16.1.10):

<img width="593" height="635" alt="Ping from Faculty to web server" src="https://github.com/user-attachments/assets/285f3795-fe0b-465d-bfd7-5ff325c9f069" />


3. Web & DNS Service
Internal clients can successfully use DNS to resolve the university's domain name and access the website hosted in the DMZ.

<img width="908" height="431" alt="Working website" src="https://github.com/user-attachments/assets/4d2acf18-abff-44ed-a3e6-24cef5378f55" />



5. Security Policy Enforcement (ACL Test)
The firewall's access control list successfully blocks unauthorized traffic between VLANs. As per the security policy, a ping from the Student VLAN to the Faculty VLAN fails, confirming the rule is working as intended.

<img width="680" height="452" alt="Ping from Student to Faculty" src="https://github.com/user-attachments/assets/63e6daad-863b-4474-bc4e-13d1b9dc21af" />


🛠️ Configuration Highlights
Cisco ASA 5506-X Firewall: Configured with three security-leveled interfaces (outside, inside, dmz), static and default routes, object-based NAT/PAT rules, and interface-specific ACLs.

Layer 3 Core Switch (3650): Configured with SVIs for Inter-VLAN routing, DHCP pools for each VLAN, and 802.1Q trunk ports.
