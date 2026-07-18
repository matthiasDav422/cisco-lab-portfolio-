# Lab 01: VLANs and Inter-VLAN Routing

*Objective:* Configure VLAN 10 and VLAN 20, then route between them using Router-on-a-Stick.

*Topology:*
PC1(192.168.10.5) -> SW1 -> R1 -> SW1 -> PC2(192.168.20.10)

*Devices:* 2x 2960 Switch, 1x 2811 Router, 2x PCs

*Switch Config:*
vlan 10
 name SALES
vlan 20
 name HR
interface f0/1
 switchport mode access
 switchport access vlan 10
interface f0/24
 switchport mode trunk
*Router Config:*

interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

*Verification:*
ping 192.168.20.10 from PC1 was successful
