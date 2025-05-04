---
tags:
---
Date: 2025-05-03 : 18:43
***
## Router ID 
### Configuración Inicial
#Q 
- Comando para habilitar OPSFv2 :: `router ospf <process-id>`.
- Es buena buena practica que el `process-id` sea el mismo en :: Todos los routers OSPF

### Router ID 
#Q 
- Es un valor de... que se representa como una... e identifica a cada... :: 32 bits, IPv4, router OSPF.
- Es necesario para sincronizar las :: Bases de Datos OSPF.
- Sirve también para elegir al :: Designated Router (DR).
- Para elegir al DR se elige el router con el *router id* más.., el siguiente router más alto se define como... :: Alto, Backup Designated Router (BDR).
- Si el **router-id** no se define de forma explícita se elige como router ID el... si no hay, se elige el... :: IP de la loopback más alto, IP de la interfaz física más alto.

### Configuración Explícita de Router ID
#Q 
- Se habilita OPSF :: `router ospf <process-id>`.
- Se define router ID :: `router-id <router-id>`.
- Para checar usamos :: `show ip protocols`.

## Point2Point OSPF Networks
### Configuración OSPF con Comando `network`
#Q 
- Existen **3 formas** para configurar las redes OPSF que son :: Con wildcard, con wildcard 0 y directo en la interfaz.
- Comando para configurar cin wildcard :: `network <network-address> <wildccard-mask> area <area-id>`.
- Con wildcard 0 para ip x.x.x.x :: `network x.x.x.x 0.0.0.0 area <area-id>`
- Directo en la interfaz, primero nos metemos a la interfaz deseada..., luego prendemos OSPF... :: `interface <interface-type> <interface-id>`, `ip ospf <process-id> area <area-id>`.

### Configuración de Interfaces Pasivas



## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "<% tp.file.path(true) %>",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```