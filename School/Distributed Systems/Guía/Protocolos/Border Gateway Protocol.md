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
- Se establece loopback como objetivo de paquetes IP :: `neighbor <loopback-ip> update-source loopback <interface-id>`

### eBGP Dual-Homed Problem/Solution
#Q 
- Problem diagram :: ![[redes2-fig10.png]]
- El problema es que si estamos en R1 solo ponemos como neighbor a `192.168.1.18` y este se cae... mientras que si ponemos como neighbor a `192.168.1.18` y a `192.168.1.34` en número de los paquetes BGP se... :: No sirve de nada la redundancia, duplican.
- La solución es configurar una :: Loopback.
- Es importante recordar que como estamos en **eBGP** y se asume que las conexiones son..., entonces también hay que configurar... :: Directas, ebgp-multihop.
- En **iBGP** no es necesario una una configuración *multihop* ya que iBGP asume que las conexiones no son... y por ello se apoya de los... :: Directas, IGP.

#### Solución para Diagrama (en R1)
#Q 
- Entramos a configuración de BGP :: `router bgp 65102`.
- Configuramos a loopback como vecino :: `neighbor 172.16.1.1 remote-as 65101`
- Configuramos loopback para que reciba todas las updates :: `neighbor 172.16.1.1 update-source loopback 0`
- Configuramos para que tenga un **Time To Live (TTL) de 2** :: `neigbor 172.16.1.1 ebgp-multihop 2`
- Configuramos **rutas estáticas** para llegar a la loopback desde R1 :: `ip route 172.16.1.1 255.255.255.255 192.168.1.18` y `ip route 172.16.1.1 255.255.255.255 192.168.1.34`.

### Advertising eBGP Routes to iBGP Peers
#Q 
Si se te olvida, ve [este video](https://www.youtube.com/watch?v=KTrGzMcanZg).
- Supongamos que que tenemos AS1 y AS2 conectados por eBGP. En AS2 tenemos la red `30.30.30.0/24` que es promocionada por el router frontera de AS2 el cual tiene IP `198.51.100.3` al router frontera de AS1. Por defecto la red `30.30.30.0/24` se patrocina mediante... en los routers de AS1 con la **next-hop**  `198.51.100.3`. Para el router frontera no hay... pero para los demás está conexión es... :: iBGP, problema, unreachable.
- Para solucionar este problema asumiendo que estamos en el router frontera de AS1 y que el IP el router interno de AS1 es `12.0.0.1` decimos :: `neighbor 12.0.0.1 next-hop-self`.

### Sincronización de BGP
#Q 
- La sincronización por defecto está... por lo que hay que... para que el router BGP no promocione rutas hasta que las aprenda por... :: Deshabilitada, habilitarla, IGP.
- Para habilitar la sincronización se usa el comando :: `synchronization`.

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