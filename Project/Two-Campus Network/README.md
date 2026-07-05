# Two-Campus Enterprise Network 
# Overview

This project simulates a complete enterprise network infrastructure for an organization with two sites: a Headquarters (Centrale) and a Branch Office (Succursale), connected over a site-to-site VPN through a simulated ISP/Internet cloud. The design focuses on high availability, network segmentation, and secure inter-site communication.



# Topology Summary
# Two independent sites:
Each with its own internet edge router, core/distribution layer, access layer, and end devices.
# Site-to-site VPN tunnel:
Linking the two campuses across a shared "Internet" router, so both locations operate as a unified network.
# Redundant core routers:
At each site (R-C1/R-C2 at HQ, R-S1/R-S2 at Branch) for gateway failover.
# Redundant distribution switches:
At each site, cross-connected in a partial mesh for link and switch-level redundancy.
# Department-based access switches: 
(e.g., Transport, Market, Administration, Store, Technician, Security) connecting PCs, printers, an IP camera, and IP phones.
# Server farms: 
At each site providing Active Directory/DNS, file storage, web/mail, printing, and a replica server for redundancy.



# Key Technologies Implemented
# VLANs: 
Each department/function is segmented into its own VLAN (VLANs 10–21 across both sites) to isolate broadcast domains and improve security.
# Trunking (802.1Q): 
Trunk links carry multiple VLANs between the distribution and access layer switches.
# Spanning Tree Protocol (STP): 
Used to prevent Layer 2 loops across the redundant, cross-connected distribution switches while still allowing failover paths.
# First Hop Redundancy (HSRP): 
Dual core routers at each site provide a standby gateway so end devices keep network access if a router fails.
# Inter-VLAN Routing: 
Routers/multilayer switches handle routing between VLANs within each site.
# Site-to-Site VPN: 
Encrypted tunnel between HQ and Branch routers over the public/ISP link, allowing both locations to communicate as one private network.
# IP Addressing/Subnetting: 
Structured addressing scheme with distinct subnets per VLAN and per site, plus point-to-point subnets for router-to-router and WAN links.
# Converged Network Services: 
IP telephony (Cisco phones) and an IP security camera integrated alongside data VLANs.



# What This Project Demonstrates
Designing for high availability at both the routing and switching layers.
Applying network segmentation to reflect real organizational departments.
Building a secure, routed WAN connection between two physical locations.
Planning and documenting a structured IP addressing scheme at scale.

