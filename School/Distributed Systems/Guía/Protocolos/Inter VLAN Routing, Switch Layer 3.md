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