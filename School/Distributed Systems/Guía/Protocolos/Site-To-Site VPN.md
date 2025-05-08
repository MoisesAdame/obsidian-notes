---
tags:
---
Date: 2025-05-07 : 13:02
***
## Configuración 
> La siguiente configuración es **exclusiva de los routers frontera** (los que se conectan al ISP).

#Q  #AOSR/hdibo
- Se habilita el **paquete de seguridad**... después de habilitarlo hay que... ::  `license boot module c1900 technology-package securityk9`, rebootear el router (recuerda guardar configuración).
- Implementar **ACL's**  necesarias :: `access-list <acl-number> permit ip <source-network> <source-wildcard> <destinatioin-network> <destination-wildcard>` #AOSR/hdibo/s/e7rq

### Configuración de IKE Fase 1 ISAKMP
#Q 
- Esto se hace con el fin de establecer el... en su fase... :: Internet Key Exchange (IKE), 1.
- Primero creamos ISAKMP con una prioridad de 10 (podemos poner otra prioridad) :: `crypto isakmp policy 10`
- Luego definimos que el tipo de encripción será **AES with 256-bit key (fuerte)** :: `encryption aes 256`.
- Luego definimos que se usará una llave **previamente compartida** para la autenticación :: `authentication pre-share`
- Luego definimos **Diffie-Hellman grupo 5** (que es un método para el intercambio seguro de las llaves). Hay varios grupos pero 5 es de mediana seguridad :: `group 5`
- Luego establecemos que la llave previamente compartida será **vpnpa55** y definimos la dirección con la que se conecta el otro router al ISP :: `crypto isakmp key vpnpa55 address <peer's-ip>`.

### Configuración de IKE Fase 2 ISAKMP
#Q 
- Le decimos a router que defina IPsec fase 2 usando **AES para encriptar** y **SHA-HMAC para autenticar** :: `crypto ipsec transform-set VPN-SET esp-aes esp-sha-hmac`.
- Crear mapa criptográfico :: `crypto map VPN-MAP 10 ipsec-isakmp`.
- Añadir descripción :: `description VPN connection to R3`
- Definimos el peer, osea a donde mandar el tráfico encriptado :: `set peer <peer's-ip>`
- Adjuntarle al mapa criptográfico el transform set previamente definido (**VPN-SET**) :: `set transform-set VPN-SET`.
- Aplicar mapa criptográfico solo a la access list que definimos :: `match address <acl-number>`.

### Configuración de Mapa Criptográfico en la Interfaz que va a ISP.
#Q 
- Vamos a la interfaz que a va ISP :: `interface <interface-type> <interface-id>`
- Configuramos mapa criptográfico :: `crypto map VPN-MAP`.



## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Site-To-Site VPN.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```