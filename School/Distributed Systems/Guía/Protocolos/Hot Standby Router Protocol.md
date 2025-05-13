---
tags:
---
DSubtitleate: 2025-05-07 : 11:13
***
## Configuration 
#Q 
- Primero vas a la interfaz donde lo quieres activar :: `interface <interface-type> <interface-id>`
- Defines la version (la 2 acepta IPv4 e IPv6) :: `standby version <version-number>`.
- El `<group-number>` se pone ya que en un mismo router puede haber varios :: HSRP.
- Se define el IP del gateway virtual :: `standby <group-number> ip <virtual-gateway-io>` 
- Comando para definir prioridad :: `standby <group-number> priority <priority-value>`.
- Comando para **forzar la elección** de router activo :: `standby <group-number> preempt`.

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Hot Standby Router Protocol.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```