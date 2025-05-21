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
ip address 
no shut
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