---
tags:
---
Date: 2025-05-02 : 11:53
***
## Configuración 
### Generalidades
#Q  #AOSR/1oivq
- Diagrama :: ![[inter-valn-routing-fig1.png |300]] #AOSR/1oivq/s/158e

### Configuración Switch 1
#Q  #AOSR/4t48t
Definir VLANs
? #AOSR/4t48t/m/3vb8
name VLAN10
exit
vlan 20
name VLAN20
exit
vlan 99
name Management
exit

#Q  #AOSR/72ftj
Definir puerto fast0/1 como de acceso para VLAN 20
? #AOSR/72ftj/m/209g
interface fast0/1
switchport mode access
swicthport access vlan 20
no shutdown

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Inter VLAN Routing, Router On A Stick.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```