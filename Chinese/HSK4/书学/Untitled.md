---
tags:
---
Date: 2024-06-25 : 21:25
***
## Subtitle

- Value

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "$.path",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```
