---
tags:
---
Date: 2025-05-20 : 12:49
***
## Configuración
### Configuración de Server
#Q
La configuración IP del DHCP debe ser :: Estática
En la parte de **services** seleccionar :: DHCP

### Configuración de Router
#Q 
Nos vamos a la interfaz donde está conectado el switch que tiene el server y ponemos :: `ip helper-address <server-ip>`

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Dynamic Host Configuration Protocol.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```