---
tags:
---
Date: 2025-04-30 : 12:49
***
## Redes LAN 
### Redes Jerárquicas
#### Redes Conmutadas Sin Bordes
#Q 
- Su diseño se basa en los :: Niveles de acceso.
- Los niveles de acceso son :: Core, distribution y access.
- La **access layer** es donde se conectan :: Los usuarios.
- En **distribution layer** se implementa el... y también se ven cosas como... y... :: Ruteo, QoS, Seguridad.
- En **core layer** es la red :: Troncal.
- Una **routed LAN** permite meter cosas como :: QoS, seguridad.

### Redes Escalables
#### Definición
#Q 
- La escalabilidad es es la capacidad de una red de... sin perder... y... :: Crecer, disponibilidad, confiabilidad.
- Las redes redundantes en red Ethernet causan... para evitarlos se usa el protocolo... :: Bucles, Spanning Tree Protocol (STP.)

#### Reducen el Tamaño del Dominio de Errores
#Q 
- Error domain es el :: Área de una red afectada.
- Los enrutadores o switches multicapa generalmente se implementan en... a esta configuración se le llama... y lo bueno es que si uno falla no... :: Pares, Block switch, se cae la red.

#### Aumentan Ancho de Banda
#Q 
- El **EtherChannel** sirve para aumentar el... combina varios enlaces... en uno... :: Ancho de banda, físicos, lógico.

#### Expandir la Capa de Acceso
#Q 
- Una opción barata y flexible para expandir la capa de acceso es usar redes :: Wireless LAN (WLAN).

#### Sintonizan Protocolos de Enrutamiento
#Q 
- Para enrutar grandes redes podemos usar protocolos como :: Open Shortest Path First (OSPF).
- OSPF es un protocolo... y usa... para admitir redes de tipo... :: Link state, áreas, jerárquicas.
- Para sinconizarse los routers OPSF usan una :: Link state data base.

### Hardware de Switch
#### Conceptos Importantes
#Q 
- Los **swicthes modulares** son los que aceptan :: Más tarjetas de línea.
- La **densidad del swicth** es la cantidad de :: Puertos que tiene.

#### Switches Multicapa


## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Redes (Parte 2).md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```