## CDMX
### S-CDMX
enable
conf t

hostname S-CDMX

vlan 10
name Medics
exit
vlan 20
name Patients
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

interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,99
no shut
exit

interface fast0/1
switchport mode access
switchport access vlan 10
no shut
exit

interface fast0/2
switchport mode access
switchport access vlan 20
no shut
exit

interface fast0/3
switchport mode access
switchport access vlan 30
no shut
exit

interface fast0/4
switchport mode access
switchport access vlan 40
no shut
exit

interface fast0/5
switchport mode access
switchport access vlan 99
no shut
exit

### R-CDMX
enable
conf t

hostname R-CDMX

interface gig0/0/0
no shut
exit

interface gig0/0/0.10
encapsulation dot1Q 10
ip address 172.16.1.254 255.255.254.0


