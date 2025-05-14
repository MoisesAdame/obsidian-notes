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
El default gateway virtual es: 17.16.6.206


*Router-A*
enable
conf t

interface gig0/1
no shutdown
exit

interface gig0/1.10
encapsulation dot1Q 10
ip address 172.16.1.254 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
standby 10 priority 110
no shutdown
exit

interface gig0/2
no shutdown
exit

interface gig0/2.10
encapsulation dot1Q 10
ip address 172.16.1.253 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
standby 10 priority 110
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
ip address 172.16.1.252 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
no shutdown
exit

interface gig0/2
no shutdown
exit

interface gig0/2.10
encapsulation dot1Q 10
ip address 172.16.1.251 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
no shutdown
exit


*Router-A*
interface gigabitEthernet 0/2.10
encapsulation dot1Q 10
ip address 172.16.1.254 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
standby 10 priority 110
no shutdown
exit

interface gigabitEthernet 0/2.20
encapsulation dot1Q 20
ip address 172.16.3.254 255.255.254.0
standby version 2
standby 10 ip 172.16.3.254
standby 10 priority 110
no shutdown
exit

interface gigabitEthernet 0/2.30
encapsulation dot1Q 30
ip address 172.16.5.254 255.255.254.0
standby version 2
standby 10 ip 172.16.5.254 
standby 10 priority 110
no shutdown
exit

interface gigabitEthernet 0/2.40
encapsulation dot1Q 40
ip address 172.16.6.126 255.255.255.128
standby version 2
standby 10 ip 172.16.6.126
standby 10 priority 110
no shutdown
exit

interface gigabitEthernet 0/2.99
encapsulation dot1Q 99
ip address 172.16.6.190 255.255.255.192
standby version 2
standby 10 ip 172.16.6.190
standby 10 priority 110
no shutdown
exit

*Router-B*
interface gigabitEthernet 0/2.10
encapsulation dot1Q 10
ip address 172.16.1.253 255.255.254.0
standby version 2
standby 10 ip 172.16.1.254
no shutdown
exit

interface gigabitEthernet 0/2.20
encapsulation dot1Q 20
ip address 172.16.3.253 255.255.254.0
standby version 2
standby 10 ip 172.16.3.254
no shutdown
exit

interface gigabitEthernet 0/2.30
encapsulation dot1Q 30
ip address 172.16.5.253 255.255.254.0
standby version 2
standby 10 ip 172.16.5.254 
no shutdown
exit

interface gigabitEthernet 0/2.40
encapsulation dot1Q 40
ip address 172.16.6.125 255.255.255.128
standby version 2
standby 10 ip 172.16.6.126
no shutdown
exit

interface gigabitEthernet 0/2.99
encapsulation dot1Q 99
ip address 172.16.6.189 255.255.255.192
standby version 2
standby 10 ip 172.16.6.190
no shutdown
exit

**En Routers (Configuración de OSPF)**
