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
interface gigabitEthernet 0/2.10
encapsulation dot1Q 99
ip address 172.16.1.254/23
no shutdown
exit

interface gigabitEthernet 0/2.20
encapsulation dot1Q 99
ip address 172.16.1.254/23
no shutdown