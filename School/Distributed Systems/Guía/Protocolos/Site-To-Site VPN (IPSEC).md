---
tags:
---
Date: 2025-05-07 : 13:02
***
## Configuración 
> La siguiente configuración es **exclusiva de los routers frontera** (los que se conectan al ISP).

#Q 
- Se habilita el **paquete de seguridad**... después de habilitarlo hay que... ::  `license boot module c1900 technology-package securityk9`, rebootear el router (recuerda guardar configuración).
- Implementar **ACL's**  necesarias :: `access-list <acl-number> permit ip <source-network> <source-wildcard> <destinatioin-network> <destination-wildcard>`
- 

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Site-To-Site VPN (IPSEC).md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```