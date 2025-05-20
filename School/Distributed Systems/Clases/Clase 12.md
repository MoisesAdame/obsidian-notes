---
tags:
---
Date: 2025-05-13 : 17:08
***
## Módulo Molina 
Temas de Examen
1. Como crear VLAN's?
2. Como hacer intervlan routing
3. Levantar OSPF
4. HSRP
5. Levantar server dhcp

## Configuraciones
### SW1
enable
conf t

vlan 10
name Teachers
exit

vlan 20
name Students
exit

interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 10,20
no shut
exit

interface gig0/2
switchport mode trunk
switchport trunk allowed vlan 10,20
no shut
exit

interface fas0/1
switchport mode access
switchport access vlan 10
no shut
exit

### SW2
enable
conf t

vlan 10
name Teachers
exit

vlan 20
name Students
exit

interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 10,20
no shut
exit

interface gig0/2
switchport mode trunk
switchport trunk allowed vlan 10,20
no shut
exit

interface fas0/1
switchport mode access
switchport access vlan 20
no shut
exit

### R1
interface ser0/1/1
ip address 10.0.0.1 255.255.255.252
no shutdown
exit

interface ser0/1/0
ip address 10.0.0.5 255.255.255.252
no shutdown
exit

router ospf 10
router-id 1.1.1.1
network 10.0.0.4 0.0.0.3 area 0
network 10.0.0.1 0.0.0.3 area 0
network 192.168.10.0 0.0.0.255 area 0
network 192.168.20.0 0.0.0.255 area 0
exit

interface gig0/0/0
no shut
exit

interface gig0/0/0.10
ip address 192.168.10.253 255.255.255.0
encapsulation dot1Q 10
standby version 2
standby 10 ip 192.168.10.254
standby 10 priority 110
standby 10 preempt
no shut
exit

interface gig0/0/0.20
ip address 192.168.20.253 255.255.255.0
encapsulation dot1Q 20
standby version 2
standby 20 ip 192.168.10.254
standby 20 priority 110
standby 20 preempt
no shut
exit

### R2
interface ser0/1/0
ip address 10.0.0.2 255.255.255.252
no shutdown
exit

interface ser0/1/1
ip address 10.0.0.9 255.255.255.252
no shutdown
exit

router ospf 10
router-id 2.2.2.2
network 10.0.0.8 0.0.0.3 area 0
network 10.0.0.0 0.0.0.3 area 0
network 192.168.10.0 0.0.0.255 area 0
network 192.168.20.0 0.0.0.255 area 0
exit

interface gig0/0/0
no shut
exit

interface gig0/0/0.10
ip address 192.168.10.252 255.255.255.0
encapsulation dot1Q 10
standby version 2
standby 10 ip 192.168.10.254
no shut
exit

interface gig0/0/0.20
ip address 192.168.20.252 255.255.255.0
encapsulation dot1Q 20
standby version 2
standby 20 ip 192.168.10.254
no shut
exit

