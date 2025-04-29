---
tags:
---
Date: 2025-04-29 : 09:36
***
## Chapter 2
### Chapter 2.4
#Q
- Definir hostname :: `hostname <name>`

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