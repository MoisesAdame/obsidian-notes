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