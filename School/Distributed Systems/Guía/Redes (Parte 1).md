---
tags:
---
Date: 2025-04-29 : 09:36
***
## Chapter 2
### Chapter 2.4
#Q
- Definir hostname :: `hostname <name>`
- Cisco solo tiene una... por lo que para acceder a ella tenemos que poner :: Consola, `line console 0`
- Poner password..., para guardarlo... :: `password <password>`, `login`
- Para ponerle password a **privileged exec** ir :: `enable secret <password>`
- Para ponerle password a las **16 virtual terminals** primero... luego... y para guardarlo... :: `line vty 0 15`, `password <password>`, `login`.
- Para **encriptar** los passwords... :: `service password-encryption`
- Para poner **banner**... sirve para cuestiones... :: `banner motd #<msg>#`, legales

### Chapter 2.5
#Q 
- Las dos files que hay de configuración son :: `running-config` y `startup-config`
- Para hacer *undo* de algo que se hizo en el `running-config` usamos... el problema es que... :: `reload`, apaga la máquina.
- Para borrar alguno de los dos files de configuración :: `erase <file-name>`.

### Chapter 2.6
#### IP Address
#Q 
- La **notación** del ip se llama :: Dotted decimal.
- Bits de **IPv4** :: 32 bits.
- Bits de **IPv6**... se representa en... :: 128, hex.

#### Interfaces & Ports
#Q 
- Las comunicaciones en red dependen de **3 cosas** :: User device interfaces, Networking interfaces y cables.
- Los switches no necesitan una... y si la usan es para que te puedas... :: IP, conectar remoto.

### Chapter 2.7
#### IP Configuration
#Q 
- La IP se puede poner de forma :: Automática o manual.
- Para poner IP de forma **automática** se usa :: Dynamic Host Configuration Protocol (DHCP).
- DHCP funciona a partir de un... que asigna... :: Server, IP's.
- Para IPv4 y IPv6 DHCP :: No es igual.

#### Switched Virtual Interface
- Es una **interfaz virtual** que le da... a una VLAN :: Ruteo de capa 3.
- Se crea al ponerle a las VLAN's :: IP's.
- Primero entramos a la vlan... y luego ponemos IP... finalmente la activamos poniendo... :: `interface vlan <1-4098>`, `ip address <ip> <mask>`, `no shutdown`

### Chapter 2.8
#Q 
- Para checar configuración de IP's :: `show ip interface brief`

## Chapter 3
### Chapter 3.1
#### Message Delivery Options
#Q 
- Los **3 tipos** son :: Unicast, multicast y broadcast.
- Diferencia entre **multicast** y **broadcast** :: **Broadcast** se manda a todos, y **multicast** se manda solo a los miembros de multicast group.


### Chapter 3.2
#### Overview
#Q 
- Los **4 principales** tipos de protocolos son :: Comunicación en red, seguridad en red, ruteo y descubrimiento de servicios.
- Ejemplos protocolos de **comunicación en red** :: IP, TCP, HTTP.
- Ejemplos de protocolos de **seguridad** :: SSH, SSL y TLS.
- Ejemplos de protocolos de **ruteo** :: OSPF y BGP.
- Ejemplos de protocolos de **descubrimiento de servicios** :: DHCP y DNS.

### Chapter 3.3
#### Network Protocol Suites
#Q 
- Son un conjunto de... que están diseñados para... :: Protocols, trabajar en conjunto.
- Las **capas de abajo** se encargan de :: Mover el mensaje en la red.
- Las **capas de arriba** se encargan de el :: Contenido del mensaje.
- El **network protocol suite** más común es :: TCP/IP.

#### TCP/IP Protocol
#Q
- En **application** tenemos :: Hyper Text Transfer Protocol (HTTP).
- En **transport** tenemos :: Transmission Control Protocol (TCP).
- En **internet** tenemos :: Internet protocol (IP).
- Y todo fluye mediante la... donde tenemos protocolos como... :: Nework layer, Ethernet o WAN.

### Chapter 3.5
#### Layered Models
#Q 
- Los **dos mas importantes** son :: OSI y TCP/IP 

#### Modelo OSI
#Q 
- Significado de OSI :: Open System Interconnection
- **Mnemotecnia** para las layes OSI :: **Please Don't Throw Sausage Pizza Away**.
- Las **layers** de OSI son :: 1) Physical 2) Data Link 3) Network 4) Transport 5) Session 6) Presentation 7) Application
- **Layer 1** describe la forma... en que se transmiten... :: Mecánica, bits.
- **Layer 2** protocolos para transmitir :: DataFrames
- **Layer 3** intercambia DataFrame en :: La network 
- **Layer 4** define como los datos se deben de :: Dividir, unir y transferir.
- **Layer 5** le da servicios a... para... :: L6, intercambio de datos.
- **Layer 6** se encarga de a los formatos de datos... haciendo cosas como... o... :: Traducirlos, *encriptar/des-encriptar*, *comprimir/descomprimir*
- **Layer 7** nos da una interfaz entre la... y las... :: Red, aplicaciones.

#### Modelo TCP/IP
#Q 
- Las **4 layers** de OSI son :: 1) Network Access 2) Internet 3) Transport 4) Application.
- **Network** es todo lo relacionado con :: Hardware.,
- **Internet** determina la mejor :: Ruta en la red.
- **Transport** Permite la comunicación de varios :: Dispositivos.
- **Application** al usuario le representa :: Los datos.

### Chapter 3.6
#### Protocol Data Units
#Q 
- **Application** :: Data.
- **Transport** :: Segment.
- **Network Layer** :: Packet.
- **Data Link** :: Frame.
- **Physical** :: Bits

### Chapter 3.7
#### Addresses
#Q 
- Los address de **Layer 2** solo sirven si dispositivos en :: Misma red.
- Los address de **Layer 3** sirven en :: Misma o diferente red.

#### Layer 3 Logical Addresses
#Q 
- Las **2 partes** de una IP son :: Network y host.

## Chapter 4
### Chapter 4.2
#### Bandwidth Terminology
#Q 
- Los **3 principales** términos son :: Latency, throughput y goodput.
- **Latency** es el tiempo con... para que datos... :: Delays, vayan de 1 punto a otro.
- **Throughput** es la cantidad de... que se... :: Bits, transfieren en un *tiempo determinado*.
- **Goodput** es la cantidad de de datos... que se... :: Usables, transfieren en un *tiempo determinado*.

### Chapter 4.4
#### Straight-trough & Crossover UTP
#Q 
- UTP significa :: Unshielded twisted pair.
- **Straight-trough** se usa para :: Dispositivos diferentes
- **Crossover** se usa para :: Dispositivos iguales.
- Ahora los cables *crossover* son... ya que existe... :: Legacy, Auto-MDIX.

### Chapter 4.5
#### Fiber vs. Copper
#Q 
- Bandwidth (copper-fib) :: 10 Mbps - 10 Gbps / 10 Mbps - 100 Gbps.
- Distance (copper-fib) :: 100 m / 100,000 m
- Tiene interferencia? (copper-fib) :: No / Si
- Costo (copper-fib) :: Más bajo / Más alto.

## Chapter 6: DataLink Layer
### Chapter 6.1




## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Redes (Parte 1).md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```