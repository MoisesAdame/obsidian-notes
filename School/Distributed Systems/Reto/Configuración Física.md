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
access-list 10 deny any

access-list 20 permit 172.16.2.0 0.0.1.255
access-list 20 permit 172.17.2.0 0.0.1.255
access-list 20 permit 172.18.2.0 0.0.1.255
access-list 20 deny any

access-list 30 permit 172.16.4.0 0.0.1.255
access-list 30 permit 172.17.4.0 0.0.1.255
access-list 30 permit 172.18.4.0 0.0.1.255
access-list 30 deny any

access-list 40 permit 172.16.6.0 0.0.0.127
access-list 40 permit 172.16.7.0 0.0.0.127
access-list 40 permit 172.16.8.0 0.0.0.127
access-list 40 deny any

access-list 50 permit 172.16.6.128 0.0.0.63
access-list 50 permit 172.17.7.128 0.0.0.63
access-list 50 permit 172.18.7.128 0.0.0.63
access-list 50 deny any

access-list 60 permit 172.16.0.0 0.0.255.255
access-list 60 deny any

interface gig0/0/0
no shut
exit

interface gig0/0/0.10
encapsulation dot1Q 10
ip address 172.16.1.254 255.255.254.0
! ip access-group 10 out
no shut

interface gig0/0/0.20
encapsulation dot1Q 20
ip address 172.16.3.254 255.255.254.0
! ip access-group 20 out
no shut

interface gig0/0/0.30
encapsulation dot1Q 30
ip address 172.16.5.254 255.255.254.0
! ip access-group 30 out
no shut

interface gig0/0/0.40
encapsulation dot1Q 40
ip address 172.16.6.126 255.255.255.128
! ip access-group 40 out
no shut

interface gig0/0/0.99
encapsulation dot1Q 99
ip address 172.16.6.190 255.255.255.192
! ip access-group 50 out
no shut

interface serial0/1/0
ip address 10.0.0.1 255.255.255.252
no shut

interface serial0/1/1
ip address 10.0.0.4 255.255.255.252
no shut

interface gig0/0/1
ip address 10.0.0.13 255.255.255.252
no shut

router ospf 10
router-id 1.1.1.1
network 172.16.0.0 255.255.254.0 area 0
network 172.16.2.0 255.255.254.0 area 0
network 172.16.4.0 255.255.254.0 area 0
network 172.16.6.0 255.255.255.128 area 0
network 172.16.6.128 255.255.255.192 area 0

router bgp 10
synchronization
redistribute connected
neighbor 10.0.0.2 remote-as 20
neighbor 10.0.0.6 remote-as 30
neighbor 10.0.0.14 remote-as 100
exit

ip dhcp excluded-address 172.16.1.250 172.16.1.254
ip dhcp excluded-address 172.16.3.250 172.16.3.254
ip dhcp excluded-address 172.16.5.250 172.16.5.254
ip dhcp excluded-address 172.16.6.123 172.16.6.126
ip dhcp excluded-address 172.16.6.185 172.16.6.190

ip dhcp pool VLAN10
network 172.16.0.0 255.255.254.0
default-router 172.16.1.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN20
network 172.16.2.0 255.255.254.0
default-router 172.16.3.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN30
network 172.16.4.0 255.255.254.0
default-router 172.16.5.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN40
network 172.16.6.0 255.255.255.128
default-router 172.16.6.126
dns-server 192.168.0.1
exit

ip dhcp pool VLAN99
network 172.16.6.128 255.255.255.192
default-router 172.16.6.190
dns-server 192.168.0.1
exit

ip nat inside source list 60 interface gigabitEthernet 0/0/1 overload

## MTY
### S-MTY
enable
conf t

hostname S-MTY

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

### R-MTY
enable
conf t

hostname R-MTY

access-list 10 permit 172.16.0.0 0.0.1.255
access-list 10 permit 172.17.0.0 0.0.1.255
access-list 10 permit 172.18.0.0 0.0.1.255
access-list 10 deny any

access-list 20 permit 172.16.2.0 0.0.1.255
access-list 20 permit 172.17.2.0 0.0.1.255
access-list 20 permit 172.18.2.0 0.0.1.255
access-list 20 deny any

access-list 30 permit 172.16.4.0 0.0.1.255
access-list 30 permit 172.17.4.0 0.0.1.255
access-list 30 permit 172.18.4.0 0.0.1.255
access-list 30 deny any

access-list 40 permit 172.16.6.0 0.0.0.127
access-list 40 permit 172.16.7.0 0.0.0.127
access-list 40 permit 172.16.8.0 0.0.0.127
access-list 40 deny any

access-list 50 permit 172.16.6.128 0.0.0.63
access-list 50 permit 172.17.7.128 0.0.0.63
access-list 50 permit 172.18.7.128 0.0.0.63
access-list 50 deny any

interface gig0/0/0
no shut
exit

interface gig0/0/0.10
encapsulation dot1Q 10
ip address 172.17.1.254 255.255.254.0
! ip access-group 10 out
no shut

interface gig0/0/0.20
encapsulation dot1Q 20
ip address 172.17.3.254 255.255.254.0
! ip access-group 20 out
no shut

interface gig0/0/0.30
encapsulation dot1Q 30
ip address 172.17.5.254 255.255.254.0
! ip access-group 30 out
no shut

interface gig0/0/0.40
encapsulation dot1Q 40
ip address 172.17.6.126 255.255.255.128
! ip access-group 40 out
no shut

interface gig0/0/0.99
encapsulation dot1Q 99
ip address 172.17.6.190 255.255.255.192
! ip access-group 50 out
no shut

interface serial0/1/0
ip address 10.0.0.2 255.255.255.252
no shut

interface serial0/1/1
ip address 10.0.0.9 255.255.255.252
no shut

interface gig0/0/1
ip address 10.0.0.17 255.255.255.252
no shut

router bgp 20
synchronization
redistribute connected
neighbor 10.0.0.1 remote-as 10
neighbor 10.0.0.10 remote-as 30
neighbor 10.0.0.18 remote-as 100
exit

router ospf 10
router-id 2.2.2.2
network 172.17.0.0 255.255.254.0 area 0
network 172.17.2.0 255.255.254.0 area 0
network 172.17.4.0 255.255.254.0 area 0
network 172.17.6.0 255.255.255.128 area 0
network 172.17.6.128 255.255.255.192 area 0
exit

ip dhcp excluded-address 172.17.1.250 172.16.1.254
ip dhcp excluded-address 172.17.3.250 172.16.3.254
ip dhcp excluded-address 172.17.5.250 172.16.5.254
ip dhcp excluded-address 172.17.6.123 172.16.6.126
ip dhcp excluded-address 172.17.6.185 172.16.6.190

ip dhcp pool VLAN10
network 172.17.0.0 255.255.254.0
default-router 172.17.1.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN20
network 172.17.2.0 255.255.254.0
default-router 172.17.3.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN30
network 172.17.4.0 255.255.254.0
default-router 172.17.5.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN40
network 172.17.6.0 255.255.255.128
default-router 172.17.6.126
dns-server 192.168.0.1
exit

ip dhcp pool VLAN99
network 172.17.6.128 255.255.255.192
default-router 172.17.6.190
dns-server 192.168.0.1
exit

## GDL
### S-GDL
enable
conf t

hostname S-GDL

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

### R-GDL
enable
conf t

hostname R-GDL

access-list 10 permit 172.16.0.0 0.0.1.255
access-list 10 permit 172.17.0.0 0.0.1.255
access-list 10 permit 172.18.0.0 0.0.1.255
access-list 10 deny any

access-list 20 permit 172.16.2.0 0.0.1.255
access-list 20 permit 172.17.2.0 0.0.1.255
access-list 20 permit 172.18.2.0 0.0.1.255
access-list 20 deny any

access-list 30 permit 172.16.4.0 0.0.1.255
access-list 30 permit 172.17.4.0 0.0.1.255
access-list 30 permit 172.18.4.0 0.0.1.255
access-list 30 deny any

access-list 40 permit 172.16.6.0 0.0.0.127
access-list 40 permit 172.16.7.0 0.0.0.127
access-list 40 permit 172.16.8.0 0.0.0.127
access-list 40 deny any

access-list 50 permit 172.16.6.128 0.0.0.63
access-list 50 permit 172.17.7.128 0.0.0.63
access-list 50 permit 172.18.7.128 0.0.0.63
access-list 50 deny any

interface gig0/0/0
no shut
exit

interface gig0/0/0.10
encapsulation dot1Q 10
ip address 172.18.1.254 255.255.254.0
! ip access-group 10 out
no shut

interface gig0/0/0.20
encapsulation dot1Q 20
ip address 172.18.3.254 255.255.254.0
! ip access-group 20 out
no shut

interface gig0/0/0.30
encapsulation dot1Q 30
ip address 172.18.5.254 255.255.254.0
! ip access-group 30 out
no shut

interface gig0/0/0.40
encapsulation dot1Q 40
ip address 172.18.6.126 255.255.255.128
! ip access-group 40 out
no shut

interface gig0/0/0.99
encapsulation dot1Q 99
ip address 172.18.6.190 255.255.255.192
! ip access-group 50 out
no shut

interface serial0/1/0
ip address 10.0.0.6 255.255.255.252
no shut

interface serial0/1/1
ip address 10.0.0.10 255.255.255.252
no shut

interface gig0/0/1
ip address 10.0.0.21 255.255.255.252
no shut

router ospf 10
router-id 3.3.3.3
network 172.18.0.0 255.255.254.0 area 0
network 172.18.2.0 255.255.254.0 area 0
network 172.18.4.0 255.255.254.0 area 0
network 172.18.6.0 255.255.255.128 area 0
network 172.18.6.128 255.255.255.192 area 0

router bgp 30
synchronization
redistribute connected
neighbor 10.0.0.4 remote-as 10
neighbor 10.0.0.9 remote-as 20
neighbor 10.0.0.22 remote-as 100
exit

ip dhcp excluded-address 172.18.1.250 172.16.1.254
ip dhcp excluded-address 172.18.3.250 172.16.3.254
ip dhcp excluded-address 172.18.5.250 172.16.5.254
ip dhcp excluded-address 172.18.6.123 172.16.6.126
ip dhcp excluded-address 172.18.6.185 172.16.6.190

ip dhcp pool VLAN10
network 172.18.0.0 255.255.254.0
default-router 172.18.1.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN20
network 172.18.2.0 255.255.254.0
default-router 172.18.3.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN30
network 172.18.4.0 255.255.254.0
default-router 172.18.5.254
dns-server 192.168.0.1
exit

ip dhcp pool VLAN40
network 172.18.6.0 255.255.255.128
default-router 172.18.6.126
dns-server 192.168.0.1
exit

ip dhcp pool VLAN99
network 172.18.6.128 255.255.255.192
default-router 172.18.6.190
dns-server 192.168.0.1
exit

## ISP
### R-ISP
enable
conf t

hostname R-ISP

interface gig6/0
ip address 10.0.0.14 255.255.255.252
no shut
exit

interface gig7/0
ip address 10.0.0.18 255.255.255.252
no shut
exit

interface gig8/0
ip address 10.0.0.22 255.255.255.252
no shut
exit

interface gig9/0
ip address 192.168.0.254 255.255.255.0
no shut
exit

router ospf 10
router-id 4.4.4.4
network 192.168.0.0 255.255.255.0 area 0
exit

router bgp 100
synchronization
redistribute connected
neighbor 10.0.0.13 remote-as 10
neighbor 10.0.0.17 remote-as 20
neighbor 10.0.0.21 remote-as 30
exit



