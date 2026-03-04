# FueVang_NetworkLab Summary

This project is a Cisco Lab midterm network build demonstrating core networking concepts covered in the first half of the course. It includes the implementation of switching, VLANs, IP addressing, routing, redundancy, STP, HSRP, and network management with Cisco devices. 

In my attempt, the network was designed with a three-tier hierarchical architecture, separating responsibilities across the Core, Distribution, and Access layers to improve scalability, redundancy, and control. All three tiers are separated by color for better distinction. 

Devices used:
11x PCs (1 Management, 1 WAN), 
7x 2960 Cisco Switches, 
4x 2911 Cisco Routers, 
2x Servers

# What Worked Well

Overall topology followed a three-tier design (Core / Distribution / Access).
Spanning Tree configuration was correct and stable.
HSRP was successfully implemented for one redundancy group.
Access-layer protections (PortFast, BPDU Guard) behaved as expected.
VLAN separation and general switching design were sound.

# What Didn’t Work / Areas for Improvement

Core 1 IP addressing was incorrect, impacting upstream routing.
Internet server was unreachable, likely due to the default route not being injected into OSPF from the correct router.
The WAN device was unreachable because the Internet router did not have a route to the WAN network.
HSRP was incomplete — a second HSRP group was needed for the 192.168.10.0/25 network.
Core Switch 2 was configured as a VTP client but should have been a VTP server.

# Key Takeaways

This project highlighted how small routing and control-plane mistakes (default route injection, VTP roles, incomplete HSRP groups) can have large end-to-end impact, even when the physical topology and switching logic are correct.
