---
tags:
---
Date: 2025-03-31 : 18:58
***
## Módulo Castañeda 
**WAN:** Conexión entre enrutadores. 

Visualizar tablas de enrutamiento: `netstat -r`

Cualquier equipo que quiera ir fuera de su segment, debe de ir a la **default gateway**


### Qué es el ping?
Un **comando**.

Lo que hace es que me permite verificar la conexión entre dos dispositivos hasta la capa de red.

Manda un mensaje ICMP: Protocolo de mensajes de control de internet. 

Envia solicitudes de eco (tipo 8 código 0) y espera solicitudes de eco (tipo 0 código cero)

WAN
- Cable Serial: Hay dos tipos DCE y DTE. 

Ver tablas de enrutamiento de Routers: `show ip route`

Enrutamiento estático entre WANS
`ip route <ip de segmento interno> <máscara> <gateway>`

**Configuration single router**
enable
configure
interface gigabitEthernet 0/0/0
ip address 192.168.21.254 255.255.255.0
no shutdown
exit

interface gigabitEthernet 0/0/1
ip address 192.168.22.254 255.255.255.0
no shutdown


enable
configure
interface gigabitEthernet 0/0/0
ip address 192.168.31.254 255.255.255.0
no shutdown
exit

interface gigabitEthernet 0/0/1
ip address 192.168.32.254 255.255.255.0
no shutdown


interface gigabitEthernet 0/0/0
ip address 192.168.41.254 255.255.255.0
no shutdown
exit

interface gigabitEthernet 0/0/1
ip address 192.168.42.254 255.255.255.0
no shutdown

**configuration WAN router**
conf t
interface Serial0/1/0
ip address 10.1.1.1 255.255.255.252
clock rate 64000
no shutdown

interface Serial0/1/1
ip address 10.1.2.1 255.255.255.252
clock rate 64000
no shutdown

interface Serial0/2/0
ip address 10.1.3.1 255.255.255.252
clock rate 64000
no shutdown
exit

conf t
interface Serial0/1/0
ip address 10.1.1.2 255.255.255.252
no shutdown
exit

conf t
interface Serial0/1/0
ip address 10.1.2.2 255.255.255.252
no shutdown
exit

conf t
interface Serial0/1/0
ip address 10.1.3.2 255.255.255.252
no shutdown
exit

conf t
ip route 10.1.1.2 255.255.255.252 Serial0/1/0
ip route 10.1.2.2 255.255.255.252 Serial0/1/1
ip route 10.1.3.2 255.255.255.252 Serial0/2/0
exit
