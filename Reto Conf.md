**VLANS**
vlan 10
name Medicos
exit
vlan 20
name Pacientes
exit
vlan 30
name IoT
exit
vlan 40
name Guests
exit
vlan 99
name Admins
exit

**En Switches**
*Piso 4*
enable
conf t

interface fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/4
switchport mode access
switchport access vlan 10
no shutdown
exit

*Piso 3*
interface fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/5
switchport mode access
switchport access vlan 10
no shutdown
exit

*Piso 2*
interface fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/5
switchport mode access
switchport access vlan 10
no shutdown
exit

*Piso 1*
interface fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/4
switchport mode access
switchport access vlan 10
no shutdown
exit

*Distribution 1*
interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface gig0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/3
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/4
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/5
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

*Distribution 2*
interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface gig0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/3
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/4
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit

interface fa0/5
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shutdown
exit




**En Routers (Configuración de HSRP y VLANS)** 
*Router-A*

enable
conf t

interface gig0/1
no shutdown
exit

interface gig0/1.10
encapsulation dot1Q 10
ip address 172.16.1.253 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
standby 10 priority 110
standby 10 preempt
no shutdown
exit

interface gig0/1.20
encapsulation dot1Q 20
ip address 172.16.3.253 255.255.254.0
standby version 2
standby 20 ip 172.16.3.254
standby 20 priority 110
standby 20 preempt
no shutdown
exit

interface gig0/1.30
encapsulation dot1Q 30
ip address 172.16.5.253 255.255.254.0
standby version 2
standby 30 ip 172.16.5.254
standby 30 priority 110
standby 30 preempt
no shutdown
exit

interface gig0/1.40
encapsulation dot1Q 40
ip address 172.16.6.125 255.255.255.128
standby version 2
standby 40 ip 172.16.6.126
standby 40 priority 110
standby 40 preempt
no shutdown
exit

interface gig0/1.99
encapsulation dot1Q 99
ip address 172.16.6.189 255.255.255.192
standby version 2
standby 99 ip 172.16.6.190
standby 99 priority 110
standby 99 preempt
no shutdown
exit

*Router-B*
enable
conf t

interface gig0/1
no shutdown
exit

interface gig0/1.10
encapsulation dot1Q 10
ip address 172.16.1.253 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
standby 10 priority 105
standby 10 preempt
no shutdown
exit

interface gig0/1.20
encapsulation dot1Q 20
ip address 172.16.3.253 255.255.254.0
standby version 2
standby 20 ip 172.16.3.254
standby 20 priority 105
standby 20 preempt
no shutdown
exit

interface gig0/1.30
encapsulation dot1Q 30
ip address 172.16.5.252 255.255.254.0
standby version 2
standby 30 ip 172.16.5.254
standby 30 priority 105
standby 30 preempt
no shutdown
exit

interface gig0/1.40
encapsulation dot1Q 40
ip address 172.16.6.124 255.255.255.128
standby version 2
standby 40 ip 172.16.6.126
standby 40 priority 105
standby 40 preempt
no shutdown
exit

interface gig0/1.99
encapsulation dot1Q 99
ip address 172.16.6.188 255.255.255.192
standby version 2
standby 99 ip 172.16.6.190
standby 99 priority 105
standby 99 preempt
no shutdown
exit

**En Routers (Configuración de OSPF)**
*Router-A*
enable
conf t

interface gig0/0
ip address 10.0.0.1 255.255.255.252
no shutdown
exit

router ospf 10
router-id 1.1.1.1
network 10.0.0.0 0.0.0.3 area 0
network 172.16.0.0 0.0.1.255 area 0
network 172.16.2.0 0.0.1.255 area 0
network 172.16.4.0 0.0.1.255 area 0
network 172.16.6.0 0.0.0.127 area 0
network 172.16.6.128 0.0.0.63 area 0

*Router-B*
enable
conf t

interface gig0/0
ip address 10.0.0.2 255.255.255.252
no shutdown
exit

router ospf 10
router-id 1.1.1.2
network 10.0.0.0 0.0.0.3 area 0
network 172.16.0.0 0.0.1.255 area 0
network 172.16.2.0 0.0.1.255 area 0
network 172.16.4.0 0.0.1.255 area 0
network 172.16.6.0 0.0.0.127 area 0
network 172.16.6.128 0.0.0.63 area 0

**En Routers (Configuración de BGP)**
*Router A*
enable
conf t

interface ser0/3/0
ip address 10.0.0.6 255.255.255.252
no shutdown
exit

router bgp 110
neighbor 10.0.0.6 remote-as 210
neighbor 10.0.0.2 remote-as 110

*Router B*
enable
conf t

interface ser0/3/0
ip address 10.0.0.9 255.255.255.252
no shutdown
exit

router bgp 110
neighbor 10.0.0.10 remote-as 210
neighbor 10.0.0.2 remote-as 110

*ISP-CDMX*
enable
conf t

interface ser0/1/0
ip address 10.0.0.6 255.255.255.252
no shutdown
exit

interface ser0/1/1
ip address 10.0.0.10 255.255.255.252
no shutdown
