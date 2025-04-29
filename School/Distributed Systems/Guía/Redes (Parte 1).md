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
- Los **4 principales** tipos de protocolos son :: Comunicación en red, seguridad en red, ruteo y descubrimiento de servicios.
- Ejemplos protocolos de **comunicación en red** :: IP, TCP, HTTP.
- Ejemplos de protocolos de **seguridad** :: SSH, SSL y TLS.
- Ejemplos de protocolos de **ruteo** :: OSPF y BGP.
- Ejemplos de protocolos de **descubrimiento de servicios** :: DHCP y DNS.




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