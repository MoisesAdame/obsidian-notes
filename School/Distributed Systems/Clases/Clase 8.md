---
tags:
---
Date: 2025-04-22 : 15:55
***
## Módulo Molina 
### OSPF v2
#### Generalidades
Cuando un router tiene varios enlaces (cada enlace es una o varias redes distintas).

Los protocolos de enrutamiento dinámico comparten información con demás routers para compartir las redes que ellos conocen.

Cuando la información entre varios routers es **coherente** se dice que la red tiene **convergencia** y esto nos permite comunicarnos completamente entre todas las redes.

Hay dos formas de hacer enrutamieno dinámico:
- **Protocolos Vector Distancia:** Nos dice si están conectados directamente, la distancia es cero. Cuando pasamos esa info un hop, la distancias que eran cero se les aumenta 1. Ejemplos de protocolos: RIP y EIGRP.
- **Protocolos de Estado del Enlace:** A cada enlace (cada edge del grafo) le asigna un valor, que es el costo que cuesta transmitir de un router a otro. Con ello podemos hacer un grafo donde los routers son los vertices y los enlaces son las aristas. Ejemplo: OSPF

#### Introducción a OSPF
Es muy bueno para **escaliabilidad** y más rápido que RIP.

OSPF es un protocolo sin clase (podemos hacer VLSM y Sider). 

Estado del enlace, es la información del enlace, cosas como: Prefijo de red, longitud de la red y costo. 

#### Características y Funciones de OSPF
Hay varios tipos de paquetes OSPF:
- Hello: Sirve para dar saludo entre routers.
- DBD: Paquete que describe las bases de datos (que son locales al principio).
- LSR: Router pregunta estado de enlace.
- 




