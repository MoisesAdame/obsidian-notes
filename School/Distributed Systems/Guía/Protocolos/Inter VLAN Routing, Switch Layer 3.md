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



vlan 70
name VLAN-70
exit
vlan 80
name VLAN-80
exit
vlan 90
name VLAN-90
exit


interface fa0/5
switchport mode access
switchport access vlan 70
exit

interface fa0/2
switchport mode access
switchport access vlan 80
exit

interface fa0/4
switchport mode access
switchport access vlan 90
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