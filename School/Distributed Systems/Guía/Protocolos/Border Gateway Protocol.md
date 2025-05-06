---
tags:
---
Date: 2025-05-05 : 12:56
***
## Configuración
### Iniciación de BGP
#Q 
- Activar **BGP** y definir AS number :: `router bgp <as-number>`
- Definir vecinos :: `neighbor {ip-address | peer-group-name} remote-as <as-number>`
- Shut down un vecino :: `neighbor {ip-address | peer-group-name} shutdown`

### Peer Groups
#Q 
- Muchas veces los vecinos se configuran igual, para ello están los :: Peer groups.
- Definir peer group :: `neighbor <peer-group-name> peer-group`
- Asignar vecinos como parte de peer group :: `neighbor <ip-address> peer-group <peer-group-name>`.

### iBGP Source IP Address Problem
#Q 
- Si estoy en un router en el que puse `neighbor x.x.x.x remote-as y` y me llega un BGP packet con IP `z.z.z.z`, entonces :: La conexión no se establece.
- Esto generalmente pasa cuando hay :: Varios paths.
- Diagrama ejemplo :: ![[redes2-fig9.png | 300]]
- En el diagrama el router D usa `neighbor 10.3.3.1 remote-as 65102` para comunicarse con router A, pero router A manda paquetes BGP a D a través de B con el ip `10.1.1.1` motivo por el cual :: La sesión no se establece.
- Una buena práctica en **iBGP** es puramente usar :: Loopbacks

#### Configuración de Loopback para Recibir Todos los Paquetes BGP
#Q 
- Se establece a la loopback como vecino :: `neighbor <loopback-ip> remote-as <as-number>`.
- Loop




## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Border Gateway Protocol.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```