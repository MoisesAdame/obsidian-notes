---
tags:
---
Date: 2025-04-28 : 18:25
***
## Módulo Reto
Cosas principales
- En las clinicas que haya access points.
- En las clínicas que tambien haya VLANs
- en las clínicas que haya ese servicio para que cuando te registres, te lleve a tu VLAN.
- La parte de afuera de las clínicas debe tener un router
- Las clínicas se deben si o si conectar con un VPN site-to-stie

- investigar como usar BGP ya sea eBGP y iBGP
- los doctores se deben conectar mediante un VPN remote access.
- Redundancia en los routers core
- Redundancia en switches (recomendo redundancia en stack)

## Módulo Castañeda
### Listas de Acceso
#### Definición
Las listas de acceso son un conjunto de instrucciones para tener mayor control con los paquetes. Filtran los paquetes.

Son el antecesor de los firewalls.

Son necesarias para los VPN's.

#### Lógica de Operación
Se crea lista con un conjunto de instrucciones como:
- Rutear
- QoS
- Etc.

Como funciona:
- Llega paquete y se prueba primera condición
- Luego con la segunda
- Luego tercera y etc...

Si no se logra, se va a un basurero porque se tiene que negar todo desde el principio.

#### Tipos de Listas de Acceso
Según el protocolo cambian.

Tener muchas listas de acceso habla de una mala administración.

Hay varias como:
- IP: Se usan con VPN o NAT
- Extended IP: 

#### Wildcard Mask
Se usan para determinar los segmentos a los que se les aplica lista