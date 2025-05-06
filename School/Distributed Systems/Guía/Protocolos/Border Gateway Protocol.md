---
tags:
---
Date: 2025-05-05 : 12:56
***
## Configuración
### Iniciación de BGP
#Q 
- Activar **BGP** y definir AS number :: `router bgp <as-number>`
- Definir vecinos :: `neighbor {ip-address | peer-group-name} remote-as <as-number>`
- Shut down un vecino :: `neighbor {ip-address | peer-group-name} shutdown`

### Peer Groups
#Q 
- Muchas veces los vecinos se configuran igual, para ello están los :: Peer groups.
- Definir peer group :: `neighbor <peer-group-name> peer-group`
- Asignar vecinos como parte de peer group :: `neighbor <ip-address> peer-group <peer-group-name>`.

### 




## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Border Gateway Protocol.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```