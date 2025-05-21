---
tags:
---
Date: 2025-05-02 : 12:13
***
## Configuración 
### Generalidades
#Q 
- Diagrama :: Aqui va diagrama

### Configuración Switch Capa 3
#Q 
Paso 1, crear VLAN's
?
vlan 10
name VLAN10
exit

vlan 20
name VLAN20
exit

#Q 
Paso 2, crear las interfaces VLAN SVI
?
interface vlan 10
ip address 192.168.10.254 255.255.255.0
no shutdown
exit

interface vlan 20
ip address 192.168.20.254 255.255.255.0
no shutdown
exit

#Q  #AOSR/6o0r3
Paso 3, configurar puertos de acceso
? #AOSR/6o0r3/m/3gva
interface fastEthernet 0/1
switchport mode access
switchport access vlan 10
no shutdown
exit

interface fastEthernet 0/2
switchport mode access
switchport access vlan 20
no shutdown
exit

#Q 
Paso 4, habilitar enrutamiento ip
?
ip routing

#Q 
Configurar puerto como routeable
?
interface \<interface-type> \<interface-id>
no switchport
ip address \<ip> \<mask>

#Q 
Configurar troncales (en caso necesario)
?
interface \<interface-type> \<interface-id>
switchport mode trunk
switchport mode trunk native vlan \<vlan-id>
switchport trunk encapsulation dot1q
(No es necesario especificar allowed vlans).



**GAMMA**
enable
conf t

hostname GAMMA

no ip domain-lookup

line console 0
logging synchronus 
password AREA 145
exit

banner motd  ¡Advertencia! Solo personal autorizado.

enable secret INTEGRA2023

line vty 0-15
password REMOTO2020
exit

service encypted password

interface gig0/0/1
ip address 10.21.0.1 255.255.240.0
no shut
exit

interface gig0/0/0
ip address 10.21.52.132 255.255.255.224
no shut
exit

router ospf 8
network 10.21.0.0 0.0.15.255 area 0
network 10.21.52.128 0.0.0.31 area 0

**ETA**
enable
conf t

hostname ETA

no ip domain-lookup

line console 0
logging synchronous 
password AREA145
exit

banner motd  ¡Advertencia! Solo personal autorizado.

enable secret INTEGRA2023

line vty 0-15
password REMOTO2020
exit

service encypted password

interface gig0/0/0
ip address 10.21.52.186 255.255.255.252
no shut
exit

interface gig0/0/1
ip address 10.21.52.190 255.255.255.252
no shut
exit

router ospf 8
network 10.21.52.184 0.0.0.3 area 0
network 10.21.52.184 0.0.0.3 area 0

**SIGMA**
enable
conf t

hostname SIGMA

no ip domain-lookup

line console 0
logging synchronous 
password AREA145
exit

banner motd  ¡Advertencia! Solo personal autorizado.

enable secret INTEGRA2023

line vty 0 15
password REMOTO2020
exit

service encypted password

interface gig0/0/0
ip address 10.21.52.178 255.255.255.248
no shut
exit

interface gig0/0/1
no shut
exit

interface gig0/0/1.100
encapsulation dot1Q 100
ip address 10.21.32.1 255.255.248.0
no shut
exit

interface gig0/0/1.200
encapsulation dot1Q 200
ip address 10.21.16.1 255.255.240.0
no shut
exit

router ospf 8
network 10.21.52.176 0.0.0.7 area 0
network 10.21.32.0 0.0.7.255 area 0
network 10.21.16.0 0.0.15.255 area 0

**TAU**
router ospf 8
network 10.21.52.176 0.0.0.7 area 0
network 10.21.48.0 0.0.3.255 area 0
network 10.21.44.0 0.0.3.255 area 0
network 10.21.40.0 0.0.3.255 area 0

vlan 70
name VLAN-70
exit

vlan 100
name VLAN-100
exit

vlan 200
name VLAN-200
exit

interface vlan 70
ip address 10.21.48.1 255.255.252.0
exit

interface vlan 80
ip address 10.21.44.1 255.255.252.0
exit

interface vlan 90
ip address 10.21.40.1 255.255.252.0
exit


## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Inter VLAN Routing, Switch Layer 3.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```