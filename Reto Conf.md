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

**En Routers**
El default gateway virtual es: 17.16.6.206


interface gigabitEthernet 0/2.10
encapsulation dot1Q 10
ip address 172.16.1.254 255.255.254.0
no shutdown
exit

interface gigabitEthernet 0/2.20
encapsulation dot1Q 20
ip address 172.16.3.254 255.255.254.0
no shutdown
exit

interface gigabitEthernet 0/2.30
encapsulation dot1Q 30
ip address 172.16.5.254 255.255.254.0
no shutdown
exit

interface gigabitEthernet 0/2.40
encapsulation dot1Q 40
ip address 172.16.6.126 255.255.255.128
no shutdown
exit

interface gigabitEthernet 0/2.99
encapsulation dot1Q 99
ip address 172.16.6.190 255.255.255.192
no shutdown
exit