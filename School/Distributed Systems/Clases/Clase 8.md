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
- LSU: Sirve para actualizar información

#### Tablas
Orden:
1. Primero se hace **tabla de vecinos**. Router determina sus vecions a un salto.
2. Luego se hace **tabla de topología**. Muestra info de todos los routers en la red. Esta es la base de SPF.
3. Finalmente se hace **tabla de enrutamiento**. Ahí se especifica el resultado de SPF. Con base en la información global, esta tabla va a ir variando, por ejemplo, si un enlace se hace más caro, entonces, usamos la tabla de topología para *recalcular* la tabla de enrutamiento.

#### Open Lint State
1. Se establecen andyacencias
2. Se intercambian anuncios de estado de enlace
3. Se crea base de datos
4. ETC

#### Características
OSPF logra ser **escalable** mediante las *areas*. Un *área* es un conjunto de routers interconectados.

Crear áreas nos permite contener el tamaño o la cantidad de información que se comunica entre los routers, haciendo que logremos una **convergencia** más rápida.

La única condición para que funcione, es que el enrutamiento sea jerárquico, es decir, como un árbol, donde haya un área 0 que sea una especie de root.

Los routers que conectan un área con otra son los llamados **enrutadores fronterizos**.

OSPF es un **protocolo de enrutamiento interno** no es como BGP.

#### OSPF v.X
OSPF v3 De forma nativa soporta IPv6.

### Comandos
Prender OSPF: `router ospf <process id>`

Cada router necesita un id, el cual sirve para ponerle nombre a los vértices: `router-id <no es un ip, es un identificador>`. Si no lo especificamos, busca la dirección IPv4 más alta (la mayor) en los loopbacks, si no hay, se va a las físicas.

Qué es un **loopback**? Es una interface lógica, fantasma. No existe físicamente, pero si responde, es como 127.0.0.1

Se usan cuando queremos simular cosas como la conexión a un ISP.










