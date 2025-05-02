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
#Q 
- Se implementan generalmente en las capas :: Core y distribución.
- Su ventaja es que a los **paquetes IP** los reenvían a una velocidad parecida a los :: Paquetes de capa 2.

### Hardware de Router
#### Requerimientos del Router
#Q 
- Los routers usan el... para routear los paquetes a su destino :: Prefijo de red.

## Redes VLAN
### Descripción General
#### Definiciones
#Q 
- Son conexiones de tipo... entre dispositivos... :: Lógicas, similares.
- Tener VLAN nos proporciona... en un mismo... :: Segmentación, switch.
- Cada VLAN tiene su propio rango de :: IP's
- Beneficios de VLAN :: Seguridad, menores costos, mayor rendimiento.

#### Tipos de VLAN
- La **VLAN 1** es la vlan, no se puede... ni... :: Nativa predeterminada, eliminar, cambiar.
- La **VLAN de datos** esta dedicada al tráfico generado por :: Usuario.
- La **VLAN nativa** se usa para enlaces de tipo :: Troncal.
- La **VLAN administración** se usa para tráfico de tipo ::  SSH/Telnet VTY.

### VLAN en un Entorno de Multiple Routing
#### Troncales de VLAN
#Q 
- Es un mismo link físico por el cual viajan varias :: VLANs
- **802.1Q** es un estándar que le pone a los frames the ethernet un... que identifican a que... :: Tag, VLAN pertenece.
- Los dispositivos en diferentes VLAN's no se pueden comunicar a menos que haya un :: Dispositivo de capa 3.

#### Identificación de VLAN con una Etiqueta
#Q 
- Tamaño del encabezado **802.1Q** mide :: 4 bytes.
- Los **4 campos** del encabezado 802.1Q son :: Tipo, prioridad de usuario, CFI y VLAN ID (VID).

#### VLAN Nativas y Etiquetado 802.1Q
#Q 
- Ambos extremos de un enlace troncal se deben configurar con la misma :: VLAN nativa.

## Inter VLAN Routing
### d


## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Redes 2.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```