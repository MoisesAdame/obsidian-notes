---
tags:
---
Date: 2025-05-01 : 17:31
***
## Configuración
### Generalidades
#Q 
- Ingresar a la VLAN :: `vlan <val-id>`
- Asignar nombre a VLAN :: `name <vlan-name>`

### Asignar VLAN a Interfaces Específicas
#Q 
- Ingresar a la interfaz deseada :: `interface <interface-id>`
- Establecer el puerto en *modo de acceso* :: `switchport mode access`.
- Asignar el puerto a una VLAN :: `switchport access vlan <vlan-id>`

### Ver información de VLAN
#Q 
- Show VLAN or VLAN's info :: `show VLAN [brief | id <vlam-id>]` 

## Troncales de VLAN
### Configurar Interfaz como Troncal
#Q 
- Ingresar a la interfaz :: `interface <interface-id>`
- Definir interfaz como troncal :: `switchport mode trunk`
- Definir VLAN nativa de interfaz :: `swicthport trunk native vlan <vlan-id>`
- Definir VLAN's admitidas por esa troncal :: `switch trunk allowed vlan <vlan-id>, <vlan-id>, <vlan-id>`

### Restablecer Enlace Troncal al Estado Predeterminado
#Q 
- Ingresar a la interfaz :: `interface <interface-id>`
- Desactivar VLAN's admitidas por esa troncal :: `switch trunk allowed vlan`.
- Desactivar VLAN nativa de interfaz :: `no swicthport trunk native vlan`.
- Restablezca el enlace troncal a un modo de acceso :: `switchport mode access`.

### Dynamic Trunking Protocol
#Q 
- Si la interfaz vecina está configurado en modo trunk, desirable, o dynamic auto se pone :: `switchport mode dynamic desirable`
- Si la interfaz vecina está configurado en modo trunk o desirable se pone :: `switchport mode dynamic auto`
- Para desabilitar DTP primero ponemos... y luego... :: `switchport mode trunk`, `switchport mode nonegotiate`.

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Virtual Local Area Network.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```