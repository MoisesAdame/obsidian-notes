---
tags:
---
Date: 2025-05-02 : 11:53
***
## Configuración 
### Generalidades
#Q  #AOSR/1oivq
- Diagrama :: ![[inter-valn-routing-fig1.png |300]] #AOSR/1oivq/s/158e

### Configuración Switch 1
#Q  #AOSR/4t48t
Definir VLANs
? #AOSR/4t48t/m/3vb8
name VLAN10
exit
vlan 20
name VLAN20
exit
vlan 99
name Management
exit

#Q  #AOSR/72ftj
Definir puerto fast0/1 como de acceso para VLAN 20
? #AOSR/72ftj/m/209g
interface fast0/1
switchport mode access
swicthport access vlan 20
no shutdown

#Q 
Permitir acceso de forma remota através de la VLAN 99
?
interface vlan 99
ip address 192.168.99.1 255.255.255.0
no shutdown 
exit
ip default-gateway 192.168.99.254

#Q 
Definir la interfaz gigabit 0/1 como troncal
?
interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 20
no shutdown

### Configuración Switch 2
#Q 
Definir VLANs
?
vlan 10
name VLAN10
exit
vlan 20
name VLAN20
exit
vlan 99
name Management
exit

#Q 
Definir puerto fast0/1 como de acceso para VLAN 10
?
interface fast0/1
switchport mode access
swicthport access vlan 10
no shutdown
exit

#Q 
Permitir acceso de forma remota através de la VLAN 99
?
interface vlan 99
ip address 192.168.99.2 255.255.255.0
no shutdown 
exit
ip default-gateway 192.168.99.254

#Q 
Definir la interfaz gigabit 0/1 como troncal
?
interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 10,20
no shutdown

#Q 
Definir la interfaz gigabit 0/2 como troncal 
?
interface gig0/2
switchport mode trunk
switchport trunk allowed vlan 20
no shutdown

### Configuración del Router 0
#Q 
Definir subinterfaces y activar interfaz
?
interface gig0/0/0.10
encapsulation dot1Q 10
ip address 192.168.10.254 255.255.255.0
no shutdown
exit

interface gig0/0/0.20
encapsulation dot1Q 20
ip address 192.168.20.254 255.255.255.0
no shutdown
exit

interface gig0/0/0.99
encapsulation dot1Q 99
ip address 192.168.99.254 255.255.255.0
no shutdown
exit

interface gig0/0/0
no shutdown

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Protocolos/Inter VLAN Routing, Router On A Stick.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```