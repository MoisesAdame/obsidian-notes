---
tags:
---
Date: 2025-05-07 : 11:13
***
## Configuration 
#Q 
- Comando para definir prioridad :: `standby priority <priority-value>`.
- Comando para **forzar la elección** de router activo :: `standby preempt`.
- 



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