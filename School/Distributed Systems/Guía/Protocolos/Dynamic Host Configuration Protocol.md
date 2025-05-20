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

### Configuración de Router como DHCP Server
#Q 
- Definimos y entramos a la pool :: `ip dhcp pool <pool-name>`
- Definimos la red de esa pool :: `network <network-address> <network-mask>`
- Se define el default gateway :: `default-router <ip-gateway>`
- Para definir cuales ips excluir nos salimos a conf y ponemos :: `ip dhcp excluded-address <ip-inferior> <ip-superior>`

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