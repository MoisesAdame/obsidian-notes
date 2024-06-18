---
tags:
---
Date: {{date}} : {{time}}
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
