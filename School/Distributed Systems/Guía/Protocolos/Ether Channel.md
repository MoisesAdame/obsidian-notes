---
tags:
---
Date: 2025-05-01 : 16:51
***
## Detalles
#Q 
- Para que funcione todas las interfaces de EtherChannel deben tener :: Misma VLAN
- El duplex debe ser :: El mismo.
- Por defecto EtherChannel no está :: Habilitado.

## Configuración
#Q 
- Primero entramos al rango de interfaces afectado :: `interface range <interface-tye> <interface-id-range>`
- Luego creamos nuestro **channel group** :: `channel-group <channel-group-id> mode active`
- Luego, nos metemos a nuestra interfaz **channel group** :: `interface port-channel <channel-group-id>`
- Definimos esa interfaz como **troncal** porque por el deben de pasar varias vlans :: `switchport mode trunk`
- Definimos las vlans que pueden pasar por ese troncal :: `switchport trunk allowed vlan <vlan-id>,<vlan-id>,<vlan-id>`

## Detectar Si Funciona o No
#Q 
- Se usa el comando :: `show etherchannel summary`.
- Si *no está activo* veremos... si *está activo* veremos... :: `Po1(SD)`, `Po1(SU)`

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Ether Channel.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```
