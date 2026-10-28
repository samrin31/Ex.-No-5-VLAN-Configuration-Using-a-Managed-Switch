## Ex. No: 5  VLAN Configuration Using a Managed Switch
## Date:28.10.2026
________________________________________
# Objective
To configure Virtual Local Area Networks (VLANs) on a managed switch and verify that hosts within the same VLAN can communicate while others cannot.
________________________________________
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Managed Switch (e.g., 2960)<br>
•	4 PCs<br>
•	Straight-through Ethernet cables<br>
________________________________________
# Network Topology Diagram
Description:<br>
•	PC0 and PC1 are assigned to VLAN 10.<br>
•	PC2 and PC3 are assigned to VLAN 20.<br>
•	All PCs are connected to different ports on the same switch.<br>
<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 29 59 PM" src="https://github.com/user-attachments/assets/5d36ff94-8ad0-4916-aa07-6153ad8e7d56" />

________________________________________
# IP Addressing Table
Device	VLAN	IP Address	Subnet Mask	Port<br>
PC0	10	192.168.10.1	255.255.255.0	FastEthernet0/1<br>
PC1	10	192.168.10.2	255.255.255.0	FastEthernet0/2<br>
PC2	20	192.168.20.1	255.255.255.0	FastEthernet0/3<br>
PC3	20	192.168.20.2	255.255.255.0	FastEthernet0/4<br>
________________________________________
# Procedure
1.	Open Cisco Packet Tracer and add 4 PCs and 1 Switch.<br>
2.	Connect PC0–PC3 to switch ports FastEthernet0/1 to FastEthernet0/4 respectively.<br>
3.	Assign static IP addresses to each PC as per the IP table.<br>
4.	Enter the Switch CLI and create two VLANs:<br>
o	VLAN 10 for PC0 and PC1<br>
o	VLAN 20 for PC2 and PC3<br>
5.	Assign the respective switch ports to their VLANs.<br>
6.	Use the ping command from PC0 to PC1 (should succeed).<br>
7.	Try pinging from PC0 to PC2 (should fail — different VLANs).<br>
________________________________________
# Commands Used (Switch CLI)
bash<br>
CopyEdit<br>
Switch> enable<br>
Switch# configure terminal<br>

Switch(config)# vlan 10<br>
Switch(config-vlan)# name STAFF<br>
Switch(config-vlan)# exit<br>

Switch(config)# vlan 20<br>
Switch(config-vlan)# name STUDENTS<br>
Switch(config-vlan)# exit<br>

Switch(config)# interface range fastethernet0/1 - 2<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 10<br>
Switch(config-if-range)# exit<br>

Switch(config)# interface range fastethernet0/3 - 4<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 20<br>
Switch(config-if-range)# exit<br>
________________________________________
# Output (Screenshots)
•	VLAN configuration on switch<br>
•	PC IP settings<br>
•	Successful ping between PCs in the same VLAN<br>
•	Failed ping between PCs in different VLANs<br>

## configuration
<img width="1600" height="997" alt="WhatsApp Image 2026-10-28 at 12 29 59 PM (1)" src="https://github.com/user-attachments/assets/53c3252c-8252-495c-a5cf-6591b7d3d37d" />
<img width="1600" height="995" alt="WhatsApp Image 2026-10-28 at 12 30 00 PM (1)" src="https://github.com/user-attachments/assets/d9632153-f7a1-45d8-b804-49fccf9fca53" />
<img width="1600" height="997" alt="WhatsApp Image 2026-10-28 at 12 30 01 PM" src="https://github.com/user-attachments/assets/3243c68e-f9dc-4880-aaf5-a814a78ceb88" />
<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 30 00 PM" src="https://github.com/user-attachments/assets/67760c3f-d530-4ed5-8df0-ccfc5e57fa39" />
<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 30 02 PM (1)" src="https://github.com/user-attachments/assets/067d2163-f59e-41d0-80b8-f732a39b3140" />
<img width="1600" height="994" alt="WhatsApp Image 2026-10-28 at 12 30 02 PM" src="https://github.com/user-attachments/assets/f56ecb6e-e2ba-4f86-889e-279729f28077" />

## ping result
<img width="1600" height="995" alt="WhatsApp Image 2026-10-28 at 12 30 04 PM (1)" src="https://github.com/user-attachments/assets/04aec09f-0fb5-4cf2-8597-2528621859aa" />
<img width="1600" height="997" alt="WhatsApp Image 2026-10-28 at 12 30 04 PM" src="https://github.com/user-attachments/assets/1481e59d-1519-4b84-bbc2-c147ea2142aa" />
<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 30 03 PM" src="https://github.com/user-attachments/assets/fcdc814f-775c-44d3-bd22-c5d951552d74" />

________________________________________
# Result
Successfully created and configured VLANs on a managed switch. Verified that only PCs within the same VLAN could communicate with each other.

