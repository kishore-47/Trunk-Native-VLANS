Trunk Native VLANs – Cisco Packet Tracer

This project demonstrates the configuration of a Trunk Native VLAN in Cisco Packet Tracer, explaining how untagged traffic is handled when passing through trunk links.

📘 Project Overview

In this topology, two switches are connected with a trunk link. By default, VLAN 1 is the native VLAN, meaning traffic on this VLAN is sent untagged. The configuration is updated to assign a different native VLAN, showing how trunk links manage VLAN tagging.

Key Advantages:

Allows untagged traffic to travel across trunks securely.

Reduces misconfigurations by assigning a specific native VLAN.

Provides a method to segregate management traffic from user VLANs.

🖥️ Network Topology

Components Used:

Switches: 2 × Cisco 2960

PCs: 2 × PC-PT

Cables: Copper Straight-Through (PC–Switch), Copper Cross-Over (Switch–Switch)

IP Address Plan
Device	VLAN	IP Address	Subnet	Connected To
PC0	99	192.168.99.1	255.255.255.0	Switch0 Fa0/3
PC1	99	192.168.99.2	255.255.255.0	Switch1 Fa0/3
📂 Files
File Name	Description
trunk_native_vlan.pkt	Cisco Packet Tracer project file
README.md	Project documentation
topology_screenshot.png	Network diagram image
⚙️ Configuration Steps

1️⃣ Create VLANs

Switch(config)# vlan 99


2️⃣ Assign Access Ports

Switch(config)# interface fa0/3
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 99


3️⃣ Configure Trunk

Switch(config)# interface fa0/1
Switch(config-if)# switchport mode trunk


4️⃣ Change Native VLAN on Trunk

Switch(config-if)# switchport trunk native vlan 99


5️⃣ Verify

Switch# show interfaces fa0/1 switchport

🎯 Learning Objectives

Understand the default behavior of native VLANs.

Learn how to configure a custom native VLAN on trunk links.

Troubleshoot untagged traffic issues in VLAN environments.

🧠 Key Notes

By default, VLAN 1 is native on all trunks.

Changing the native VLAN helps in network security and organization.

Both sides of the trunk must have the same native VLAN to avoid mismatches.

💡 Author

Kishore Anand M
🎓 B.Tech IT | 🧠 Pre-final Year
🔧 Aspiring Network Engineer | 💡 AI & No-Code Tools Explorer

🛡️ Correct native VLAN configuration ensures smooth inter-switch communication and security.
