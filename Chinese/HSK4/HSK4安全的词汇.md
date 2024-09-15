---
tags:
  - hsk4
---
日期: 2024年06月28日
***
## 闪卡
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "Chinese/HSK4/书学",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```
