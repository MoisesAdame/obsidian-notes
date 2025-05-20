---
tags:
---
Date: 2025-05-20 : 13:56
***
## VLANS
### En Switches
#### Definir VLAN
`vlan <vlan-id>`
`name <vlan-name>`

#### Definir Interfaz Troncal (Lleva más de 1 VLAN)
`interface <interface-type> <interface-id>`
`switchport mode trunk`
`switchport trunk allowed vlan <vlan-id1>,<vlan-id2>,...`

#### Definir Interfaz de Acceso (Lleva solo 1 VLAN)
`interface <interface-type> <interface-id>`
`switchport mode access`
`switchport access vlan <vlan-id>`

## Inter-VLAN Routing
### En Routers
#### Definir Subinterfaces
`interface <interface-type> <interface-id>`
`no shutdown`
`exit`
`interface <interface-type> <interface-id>.<subinterface-id>`
`encapsulation dot1Q <vlan-id>`
`ip address <gateway-ip>`
`IF HSRP IS CONFIGURED IT IS DONE HERE`

## OSPF
### En Routers
#### Configuración Inicial
`router ospf <process-id>`
`router-id <router-id (parece ip)>`
`network <network-address> <network-wildcard> area <area-numer>`
`passive-interface <interface-type> <interface-id>``

`network-address is for the networks that connect opsf routers and the internal networks`

#### Configuración de Gateway of Last Resort
Definir ruta:
`ip route 0.0.0.0 0.0.0.0 [next-hop-address | exit-intf]`
Propagar ruta:
`default-information originate`

## HSRP
### En Routers
#### Router con Prioridad
El group number por buena practica se cambia por cada VLAN.
Esta configuración se hace en cada subinterfaz
`standby version 2`
`standby <group-number> ip <gateway-ip>`
`standby <group-number> priority <mayor a 100>`
`standby <group-number> preempt` para forzar.

## Server DHCP
### Utilizando Server Designado
Configurar IP de server dhcp y en servicios hacer la configuración de DHCP
En

### Utilizando Router


