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
### Funcionamiento
#Q 
- No hay comunicación entre VLAN's a menos que haya :: Dispositivo capa 3.
- Inter-VLAN routing se encarga de mandar información de :: Una VLAN a otra VLAN.
- Las **3 formas** de lograr esto son :: Legacy, router-on-a-stick y usando SVI's en switch capa 3.
- Para organizaciones pequeñas y medianas se recomienda..., para medianas y grandes se recomienda :: Router-on-a-stick, SVI's en switch capa 3.

### Legacy Inter VLAN
#Q 
- Para cada VLAN diferente se usaba :: Una interfaz en el router.
- Sirve pero el problema es que no es :: Escalable.
- Diagrama :: ![[redes2-fig1.png | 300]]

### Router-On-A-Stick Inter VLAN Routing
#Q 
- En vez de como el legacy todas las VLAN's viajan en :: Una misma interfaz.
- La interfaz del switch se configura como... y la en la interfaz del router se configuran... :: Troncal, subinterfaces
- Cuando el tráfico etiquetado de VLAN entra en la interfaz del router, esta se reenvía a... después se decide a que interfaz mandarla, si la interfaz de salida está configurada como una subinterfaz 802.1q,  las tramas se etiquetan con la... :: La subinterfaz indicada, nueva VLAN.

### Inter VLAN routing en Switch Capa 3
#Q 
- Este ese el método :: Más moderno y escalable.
- Utiliza las :: Switched Virtual Interface (SVI)
- Por cada VLAN se crea una :: SVI.
- Una SVI hace las mismas funciones que haría una :: Interfaz del enrutador.
- Es más rápido que router-on-a-stick porque todo switching y routing se hacen mediante el :: Hardware.
- No se limita a un enlace porque se pueden usar :: EtherChannels.
- La **única desventaja** es que switches de capa 3 son :: Más caros.
- Diagrama :: ![[redes2-fig2.png | 300]]

## Open Shortest Path First
### Características y Funciones
#Q 
- Es un protocolo de ruteo de tipo... fue desarrollado como alternativa a los protocolos de tipo... como... :: Link state, vector distance, RIP.
- A comparación de RIP su convergencia es... y es mejor para... :: Más rápida, escalabilidad.
- Se dice que OSPF es un protocolo... ya que en sus mensajes de actualización incluye la... :: Sin clase, máscara de red.
- Para ser escalable usa el concepto de :: Áreas.
- En OSPF un **link** puede ser una... o también un... :: Interfaz de router, segmento de red que conecta dos routers.
- La **información** de los links de OSPF se conoce como... e incluye cosas como el..., la... y el... :: Link state, prefijo de red, longitud del prefijo, costo.
- Todos los protocolos de ruteo usan... los cuales sirven para formar... que son... por el protocolo :: Mensajes, estructuras de datos, usadas.

### Componentes de OSPF
#Q 
- Los **3 componentes** de OPSF son :: Base de datos de adyacencia, link state data base (LSDB) y base de datos de reenvío.
- La **Adjacency Data Base** es nos muestra los routers... y para cada router es... :: Vecinos, única.
- Comando para ver la **adjacency database** :: `show ip ospf neighbor`
- La **Link State Data Base** nos muestra la info de... representa la... las LSDB para todos los routers son... :: Todos los routers de red, topología de red, iguales.
- Comando para ver la **Link State Data Base** :: `show ip ospf database`
- La **Base de Datos de Reenvío** se puede entender como una... para cada router es... y nos dice a los paquetes cosas como... :: Tabla de ruteo, diferente, como y a donde enviar paquetes.
- Comando para ver la **Base de Datos de Reenvío** :: `show ip route`.
- Para armar la link state database el protocolo usa el algoritmo... cada router se pone como la... del árbol y así calcula las... y con ello define la... :: Shortest path first de Dijsktra, raíz, mejores rutas, tabla de routeo.

### Operación de Link State
#Q 
- Este proceso se encarga de que los routers lleguen a :: Su estado de convergencia.

### Área única y Multiárea OSPF
#Q 
- Un **área OSPF** es un conjunto de... los cuales comparten la misma... en sus... :: Routers, información de *link state*, link state databases.
- **OPSF de área única** es cuando todos los... están en un mismo... la mejor práctica es usar el... :: Routers, área, área 0.
- **OSPF multi-área** son varias áreas con... todas las áreas deben conectarse al área... los routers que se encargan de ello se llaman... :: Jerarquía, troncal (área 0), Area Border Routers (ABR).

### OSPF Multi-Área
#Q 
- Esta arquitectura ofrece varios :: Beneficios.
- Las **tablas de ruteo** son más :: Pequeñas.
- Las **actualizaciones de link state** son :: Menos.
- El cálculo de SPF es :: Más rápido.

### OSPFv3
#Q 
- Es **casi igual** que OSPFv2 pero :: Utiliza IPv6.

## Wide Area Networks
### Purpose
#### LAN's y WAN's
#Q 
- Las WAN's conectan zonas geográficas :: Lejanas.
- Las WAN's tienen ancho de banda... en distancias... :: Altas, largas.

#### Private WAN's
#Q 
- Private WAN's are dedicated to :: One customer.
- **Public WAN's** is provided by an :: ISP.

#### WAN Topologies
##### Point To Point
#Q 
- Diagrama :: ![[redes2-fig3.png | 300]]
- Desventaja es que si se necesitan muchas puede ser :: Caro.

##### Hub-And-Spoke
#Q 
- Diagram :: ![[redes2-fig4.png | 300]]
- La única interfaz del hub es... por los demás routers :: Compartida.

##### Dual-Homed
#Q 
- Diagram :: ![[redes2-fig5.png | 300]]
- Tiene la **ventaja** de que ofrece mayor :: Redundancia, balanceo de cargas, y procesamiento.
- La **desventaja** es que es más :: Difícil y caro de implementar.

##### Fully Meshed
#Q 
- DIagrama :: ![[redes2-fig6.png | 300]]
- Es la topología más tolerante a :: Fallas.

##### Partially Meshed
#Q 
- Diagram :: ![[redes2-fig7.png | 300]]

#### Carrier Connections
#Q 
- **Single carrier** es cuando te conectas a :: Solo un proveedor.
- **Dual Carrier** es cuando te conectas a :: Dos proveedores.
- Dual carrier aumenta... y los SLA's se deben de negociar de forma... :: Redundancia, separada.

### WAN Operation
#### WAN's In The OSI Model
#Q 
- WAN no es solo un estándar, tiene varios en la layer :: 1 y 2.

#### Common WAN Terminology
#Q 
- **Data Terminal Equipment (DTE)** es el dispositivo que conecta :: Las LAN's con WAN's.
- **Data Communications Equipment (DCE)** dispositivo que se comunica con :: Proveedor.
- **Customer Premises Equipment (CPE)** son :: DTE y DCE.
- **Point Of Presence (POP)** es el punto donde se conecta el subscriptor al :: Proveedor de servicio.
- **Demarcation Point** lugar físico que separa al... del equipo del... :: CPE, proveedor de servicio.
- **Central Office (CO)** es la oficina local del... que conecta al... con la... :: Proveedor de servicio, CPE, red.
- **Local Loop (last mile)** es el... que conecta... con... :: Cable, CPE, CO.
- **Toll Network** es toda la red del :: Proveedor de servicio.
- Diagrama :: ![[redes2-fig8.png | 300]]

#### Serial Communication
#Q 
- Comunicación serial es cuando se usa solo un... mientras que la **paralela** es cuando se usan... Cable, varios.
- La comunicación paralela necesita... pero es sensitiva a... :: Sincronización, distancia.

#### Fiber Optic Standards
#Q 
- Estándar global para fibra óptica :: Synchronous **Digital Hierarchy (SDH).**
- Estándar norteamericano para fibra óptica :: **Synchronous Optical Networking (SONET)**
- **Dense Wavelength Division Multiplexing (DWDM)** permite aumentar capacidades de... y... enviando múltiples streams de datos en diferentes..., proceso que se conoce como... :: SDH, SONET, wavelengths, multiplexing.

### Traditional WAN Connectivity
#### Options
#Q 
- Las WAN's aparecen en... y en ese momento las organizaciones buscaban interconectarse :: 1980.
- Se logró usando líneas... o usando servicios... :: Dedicadas, switcheados.

#### Common WAN Terminology
#Q 
- Las **leased lines** del service provider eran lineas :: Point-To-Point.
- Son **leased** porque la organización :: Pagaba mensualmente por usarlos.
- Si bien son las más... también son las más... :: Sencillas de instalar, costosas.

#### Packet-Switch Options
#Q 
- Divide los datos en... que se routean en una... :: Paquetes, red.
- Las dos opciones **legacy** son :: Frame relay, asynchronous transfer mode (ATM)

### Modern WAN Connectivity
#### Modern WAN Connectivity Options
#Q 
- **Dedicated Broadband** usa fibra... para conectar ubicaciones... :: Obscura, remotas.
- **Packet Switched** usa... y también usa... para poder conectarse a proveedor sin importar las tecnologías de... :: Metro Ethernet, MLPS, acceso.
- **Internet Based Broadband** usan el... como infraestructura WAN :: Internet.

#### Ethernet WAN
#Q 
- Ethernet WAN se basa en cableado con :: Fibra óptica.
- Actualmente es mas común que cosas como :: Serial point-to-point, Frame Relay and ATM WAN.
- Sus ventajas es que es más :: Barato y fácil de administrar.

#### MPLS
#Q 
- Significa :: Multi Protocol Label Switching.
- Logra interconectar clientes sin importar su :: Método de acceso.
- Ejemplos de diferentes **métodos de acceso** :: Ethernet, frame relay, etc.
- No importa el tipo de protocolo ya sea... o... MPLS los... :: IPv4, IPv6, encapsula.

### Internet-Based Connectivity
#### Internet-Based Connectivity Options
#Q 
- Es una alternativa a usar opciones de WAN :: Dedicadas.
- Hay **2 tipos** de opciones :: Wired y Wireless.
- **Wired Options** usan cableado permanente como... y tienen ventajas como ancho de banda... y reducción de... :: Fibra óptica, consistente, latencia.
- **Wireless Options** son menos... porque para transmitir datos usan... pero son fácilmente... :: Caras, ondas de radio,  afectadas.

### Wired Technologies
#### Digital Subscriber Line
#Q 
- Su medio de transporte son las :: Líneas de teléfono.
- Hay **2 tipos** de DSL :: Asimétrico y simétrico.
- La **bandwidth** del asimétrico es mayor en... que en... :: Descarga, carga.
- El **protocolo** usado para conexiones DSL es... y es de capa... :: PPP, 2.
- PPP sirve para al subscriptor.... y también le puede asignar una... :: Autenticarlo, IPv4 pública.

#### Cable Technology
#Q 
- El medio de transporte de datos es :: Cable coaxial.
- Para **agregarle ancho de banda** a un sistema de cables se usa el estándar :: Data Over Cable Service Interface Specification (DOCSIS).

#### Optical Fiber
#Q 
- Cuando se instala fibra óptica a un lugar se dice :: Fiber to the x (FTTx).
- FTTx nos da el mayor :: Ancho de banda.
- Tenemos **FTTH** que es..., **FTTB** que es... y **FTTN** que es... :: Fiber to the Home, Fiber to the Building, Fiber to the Node/Neighborhood.

### Wireless Technologies
#Q 
- Las **4 principales** son :: Municipal Wi-Fi, cellular, satellite internet y WiMAX.
- WiMAX significa... es muy parecido a... :: Worldwide Interoperability for Microwave Access, cellular.

### VPN Technology
#Q 
- Una VPN es una conexión... entre dos redes... a través de una red... :: Encriptada, privadas, pública.
- Hay **2 tipos** de VPN's :: Site-to-stie VPN's y remote access.
- Las **site-to-site vpn's** se configuran en... los clientes ni... :: Los routers, se dan cuenta que existen.
- En las **remote access VPN's** el usuario es consciente que :: Inicia una conexión.

### ISP Connectivity Options
#Q 
- Las **4 formas** son :: Single-homed, dual-homed, multihomed y dual-multihomed.
- La forma más barata y que no nos da redundancia es :: Single-homed.
- La que ofrece **redundancia y balance de cargas** pero si ISP muere, se pierde la conexión es :: Dual-homed.
- En la que nos conectamos a varios ISP's es :: Multihomed.
- La topología **más resiliente** y la **más cara** es :: Dual-multihomed.

## Border Gateway Protocol
### BGP Terminology, Concepts and Operation
#### IGP vs EGP
#Q 
- IGB significa... trabaja dentro de un mismo... algunos ejemplos son... :: Interior Gateway Protocol, Autonomous System (AS), RIP, OSPF, EIGRP
- EGP significa... trabaja en.... por ejemplo... :: External Gateway Protocol, diferentes AS, BGP.

#### Autonomous System
#Q 
- Un **Autonomous System** es un conjunto de... que comparten políticas de routeo... :: Routers, similares.
- Generalmente una AS pertenece a una :: Organización
- Cuando un AS se conecta al exterior usando un EGP se le debe asignar un... que son administrados por... :: AS number, Internet Assigned Numbers Authority (IANA).
- Cada región administra sus AS numbers a través de de los :: Regional Internet Registries (RIRs).
- Los AS numbers tienen... bits por lo que van del... al... :: 16, 1, 65,535.

#### BGP Basics
#Q 
- El internet es una colección de... los cuales están entre si..., lo cual se logra mediante... :: AS, interconectados, BGP.
- BGP is a... protocol :: Path vector.
- **BGP** es el único protocolo que usa... porque por ejemplo **OPSF** opera sobre... mientras que **RIP** usa... :: TCP, IP, UDP.

#### Peers = Neighbors
#Q
- Se llaman **BGP Peers** a aquellos routers que han establecido una conexión... donde intercambian información de routeo... :: TCP, BGP.
- Cada router que corra **BGP** se llama :: BGP Speaker.

#### BGP vs IGP's
#Q 
- A comparación de los IGP's, BGP no toma decisiones basándose en :: La ruta mas corta.
- BGP se basa en... para definir su routeo :: Políticas.

#### Using BGP in an Enterprise Network
#Q 
- Los **2 tipos** de BGP son :: Internal BGP y External BGP.
- Cuando BGP corre en routers de un mismo AS es :: iBGP.
- Cuando BGP corre en routers de diferentes AS es :: eBGP.

#### iBGP
#Q 
- Un **Transit AS** es un AS que lleva tráfico de un... a... :: A, otro AS.
- Si bien en un **Transit AS** se pueden redistribuir eBGP en OSPF (en sus routers internos), lo recomendable es que en los routers internos se implemente... ya que es mucha información para OSPF procesar. :: iBGP
- iBGP también lo pueden usar... ya que todos sus routers deben tener conocimiento de rutas... :: Nontransit AS, externas.

#### BGP Path Vector Characteristics
#Q 
- La información de un **path vector** es una lista de los... que se da... para llegar a la red... :: AS numbers, hop-by-hop, destino.

#### Usar y no Usar BGP
#Q 
- Se **debe usar** cuando nuestro AS se conecta a..., también si nuestro AS funge como..., o también si se quieren manipular las políticas para... :: Varios otros AS, transit AS, entrar o salir del AS.
- **No se debe usar** si solo tenemos una conexión a... o a otro..., tampoco usar si los edge routers tienen... :: Internet, AS, poca memoria y/o procesamiento.

#### Sincronización BGP
#Q 
- La **regla de sincronización de BGP** nos dice que un router no puede usar o promocionar a un vecino... una ruta aprendida por iBGP a menos que esa ruta sea... o aprendida por... :: Externo, local, un IGP.
- Si la **sincronización está activa** iBGP se espera a que... propague las rutas dentro del AS y luego la promociona a... :: El IGP, vecinos externos.
- La **regla de sincronización BGP** evita que haya... y errores de... :: Loops, routeo.
- Por defecto en las nuevas actualizaciones del IOS de Cisco la **sincronización BGP** está :: Desactivada.

## Access Control List








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