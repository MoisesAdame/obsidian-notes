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

access-list 10 permit 172.16.0.0 0.0.1.255
access-list 10 permit 172.17.0.0 0.0.1.255
access-list 10 permit 172.18.0.0 0.0.1.255

access-list 20 permit 172.16.2.0 0.0.1.255
access-list 20 permit 172.17.2.0 0.0.1.255
access-list 20 permit 172.18.2.0 0.0.1.255

access-list 30 permit 172.16.4.0 0.0.1.255
access-list 30 permit 172.17.4.0 0.0.1.255
access-list 30 permit 172.18.4.0 0.0.1.255

access-list 40 permit 172.16.6.0 0.0.0.127
access-list 40 permit 172.16.7.0 0.0.0.127
access-list 40 permit 172.16.8.0 0.0.0.127

access-list 50 permit 172.16.6.128 0.0.0.63
access-list 50 permit 172.16.7.128 0.0.0.63
access-list 50 permit 172.16.7.128 0.0.0.63

interface gig0/0/0
no shut
exit

interface gig0/0/0.10
encapsulation dot1Q 10
ip address 172.16.1.254 255.255.254.0
ip access-group 10 in
no shut

interface gig0/0/0.20
encapsulation dot1Q 20
ip address 172.16.3.254 255.255.254.0
ip access-group 20 in
no shut

interface gig0/0/0.30
encapsulation dot1Q 30
ip address 172.16.5.254 255.255.254.0
ip access-group 30 in
no shut

interface gig0/0/0.40
encapsulation dot1Q 40
ip address 172.16.6.126 255.255.255.128
ip access-group 40 in
no shut

interface gig0/0/0.99
encapsulation dot1Q 99
ip address 172.16.6.190 255.255.255.192
ip access-group 50 in
no shut

