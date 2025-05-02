---
tags:
---
Date: 2025-05-02 : 12:13
***
## Configuración 
### Generalidades
#Q 


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