---
tags:
---
Date: 2025-05-03 : 18:43
***
## Router ID 
### Configuración Inicial
#Q 
- Comando para habilitar OPSFv2 :: `router o`

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "<% tp.file.path(true) %>",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```