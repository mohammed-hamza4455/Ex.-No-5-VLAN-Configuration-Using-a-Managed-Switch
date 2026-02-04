## Ex. No: 5  VLAN Configuration Using a Managed Switch
Date: 30-01-26
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
(Insert screenshot of your Packet Tracer setup here)<br>
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
![WhatsApp Image 2026-02-04 at 3 47 37 PM](https://github.com/user-attachments/assets/a764290e-32a7-4c94-8aa0-a28cb5c17342)
![WhatsApp Image 2026-02-04 at 3 47 37 PM](https://github.com/user-attachments/assets/ec24d44b-d040-4e5f-9581-d6f814f5b231)
![WhatsApp Image 2026-02-04 at 3 48 20 PM](https://github.com/user-attachments/assets/6ec8bb98-7343-4cb1-b3b0-b3ec089113bd)
![WhatsApp Image 2026-02-04 at 3 48 50 PM](https://github.com/user-attachments/assets/9fc64160-46d4-473d-93af-ba817079fee9)
![WhatsApp Image 2026-02-04 at 3 49 10 PM](https://github.com/user-attachments/assets/c4804a72-2e89-4a55-8fce-b0f2c35e705e)

________________________________________
# Result
Successfully created and configured VLANs on a managed switch. Verified that only PCs within the same VLAN could communicate with each other.

