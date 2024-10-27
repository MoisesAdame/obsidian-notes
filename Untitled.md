---
tags:
---
日期: <% tp.date.now("YYYY") %>年<% tp.date.now("MM") %>月<% tp.date.now("DD") %>日
***
## 词语
#Q 
Ejemplo :: 例如 (lì rú)

## 语法
### 1. 语法点
#### 特点
在这里写。

#### 语法
在这里写。

#### 例如
- 第一例如。
- 第二例如。

## 闪卡
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
