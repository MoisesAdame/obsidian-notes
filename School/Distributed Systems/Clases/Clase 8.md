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

Luego para la red: `network <dirección de red> <wildcard-mask (inverso de la máscara)> area <número del area>`

#### Interfaces Pasivas
Si no hay otro router en la red, se pone la red como pasiva para evitar mandar mensajes sin necesidad.

Para ponerla nos metemos a ospf y ponemos: `passive-interface <tipo-interfaz> <numero de la interfaz>`

### Formas de Configurar OPSF
La primera es con: `network <dirección de red> <wild card> area <X>`

Otra con máscara de 4 0's: `network <dirección de host> 0.0.0.0  area <X>`

### Enlaces Punto a Punto


## Módulo Cloud
### Administración del Almacenamiento
#### Introducción
A la hora de definir una base de datos, solo tener una y muchas máquinas virtuales puede ser un problema por que genera **cuellos de botella**. En el caso de agregar una nueva base de datos, estamos generando una **inconsistencia** ya que los datos de una base de datos no son los mismos de la otra base de datos.

#### Redundancia Local
Como se hacía o hace en un data center local.

**RAID** es: Redundant Array of Independent Disks.

**RAID 0 (Stripping):** Toda mi info esta en una sola máquina, apilo discos. Puedo tener disco 0, disco 1. Cada uno con sus particiones. Puedo escribir cosas de disco 1 en disco 2, y de tal forma disminuyo mi probabilidad de perder todo. El problema es que aunque mientras mas discos agreguemos, solo disminuimos la cantidad de datos perdidos, pero **seguimos perdiendo todo**. Otra ventaja es que el **performance de escritura** aumenta, ya que puedes paralelizar tus escrituras.

**RAID 1 (Mirroring):** Toda la información se copia en otro disco. La desventaja es que **pierdo el buen performance de escritura** y de hecho, ahora tengo que escribir el doble.

**RAID 5 (Stripping + Distributing Parity):** Hago tanto mirrorirng y stripting, mis mirrors están en algunos (no todos de los discos). No es el más rápido, pero es mas rápido que RAID 1. No tiene la redundancia de RAID 1, pero bajas bastante la posibilidad de perder toda tu info.

Para lograrlo, necesitamos un orquestador (software) y generalmente, todo esto se monta en el **file system**.

Kernel de la máquina es el código básico de la máquina. El **file system** vive en el kernel del OS.

El file system sabe transformar un path a pasar los datos a una ubicación dada en el disco duro.

#### Redundancia DB

##### Redundancia Activa o Activo Activo 
Las dos bases de datos están trabajando. Pero la instancia primaria es la que acepta cosas como *CRUD*, es la instancia con la que operamos principalmente. La instancia auxiliar solo puede hacer *read* para evitar conflictos.

Para que funcione la instancia primaria debe constantemente **auctualizar** la instancia auxiliar.

Esta estrategia es muy útil cuando hacemos mucho **read**.

##### Redundancia Pasiva o Activo Pasivo
Tengo una o varias instancias activas y una o varias pasivas. Las activas pueden hacer *CRUD*, y las pasivas están *apagadas* pero sigo haciendo el update constante.

Con este esquema, no solo me quedo con *read*, si no que la pasiva, toma las funciones de la activa.

#### GFS/HDFS
##### Distributed File Systems
GFS es Google File System. Como puedo almacenar un archivo en varias máquinas. Su versión open source es HDFS creado por yahoo en Hadoop.

En lugar de tener discos y apilarlos en racks, tengo **nodos/máquinas**. Un archivo se distribuye en todos ellos. Funcionan como un cluster.

La ventaja es que ya no había necesidad de **escalabilidad vertical**, ya solo era necesario traer más máquinas.

##### Operaciones
GFS/HDFS nos dan dos operaciones **lectura** y **escritura**. Los archivos se dividen en lotes de un tamaño fijo.

Supongamos que tenemos un archivo dividido en tres lotes/chunks A, B y C.

Para **read** primero leemos chuck A, luego B y luego C.

Para **write** lo *único* que puedo hacer es crear chunk D. No puedo "mochar" chunks. Para hacer un cambio en medio o al principio, tengo que porrar y reescribir todo.

Cada chunk vive en *una o muchas máquinas*. El motivo por el que se hizo así es que ahora tenemos mucho CPU y podemos procesar de forma paralela.

##### Distribución de Chunks
File system divide archivo en chunks.

Cada chuck se almacena en una máquina independiente (me da redundancia), por que si una se muere solo pierdo C. No A, B y C. Pero para evitar pérdidas, cada chunk se copia en otra máquina.

Si una máquina se muere y ve que hay pocas, se hacen mas copias.

Esto genera un problema, las máquinas no se hablan entre si, solo le reportan todas a un **servidor maestro**, el cual no almacena nada.

##### Lectura
El servidor maestro tiene un árbol donde registra todos los archivos que se almacenan en el file system.

El nodo maestro le da la **receta** al cliente para reconstruir su archivo así como donde esta ubicado cada chunk. 

La ventaja es que puede pedir de forma paralela los chunks.

Hay dos tipos de mensajes. De **control** "dame la receta". De **datos** "recuperar los chunks".

EL PROBLEMA ES EL **NODO MAESTRO**.

##### Escritura
1. Cliente le dice a nodo maestro "Quiero escribir".
2. Nodo maestro pregunta y recibe el tamaño del archivo.
3. El nodo maestro le da la "receta" de como se van a llamar y donde guardar cada *chunk*.
4. Primero solicitas escritura en la replica **más cercana** (para evitar latencia).
5. Luego la mas cercana se encarga de mandarle las copias a todos
6. Luego preguntas si todos tienen la copia.
7. Una vez que sabes que todos la tienen **primero tienen que escribir la info en la réplica principal**
8. Hasta que todas las replicas confirmen, la **replia principal** debe decirme que ya todos lo escribieron. Pero esa confirmación va al cliente. No al nodo maestro.

##### Heart Beat
De forma periódica preguntar a los nodos si tienen o no esos chunks.

Si no te contestan, es que entro en **paro**, para ello debo saber que cachos perdí, entonces el nodo maestro le dice a los nodos que tienen los cachos faltantes que lo copien en un nuevo nodo auxiliar.

##### Failover Replica
Un activo pasivo de nuestro nodo maestro. Lo hace a través de logs que se replican en un failover.

#### Ciclo de Vida Datos
##### Fases
En cada fase hay que hacerse ciertas preguntas clave:
1. **Creación de Datos:** Origen? 
2. **Almacenamiento:** Dónde se almacenan? Que tipo de DB usaré? 
3. **Uso:** Quién lo va a consumir? Cada cuánto? Se puede modificar?
4. **Compartir:** Quién mas usará los datos? En que medio los compartiré?
5. **Archivo:** Que pasará en el futuro? Hasta cuándo almacenar?
6. **Destrucción:** Cuándo borrar?

##### Optimizando el Costo
Tenemos dos variables costo por **consumo** o por **almacenamiento**

Hay dos ideas:
- Almacenamiento caliente (frecuente): Consumirlo es muy barato, almacenarlo es caro.
- Almacenamiento frío (infrecuente): Consumir es caro, pero almacenar es barato.

Por ejemplo para una tomografía que se hizo hace poco, es mejor almacenarlo en caliente, pero un estudio muy viejo, es mejor almacenarlo en frío.

Podemos poner reglas basados en el uso de los datos.

##### Creando Reglas
Si no lo usa en 30 días pásalo a uno mas frio y así sucesivamente.

##### Disaster Recovery Plan
Dentro del DRP se tiene una carrera contra reloj.

Decimos que vamos hacer y en cuánto tiempo lo vamos a arreglar.

Se hace un **documento** para saber los pasos, responsables, acciones para mitigar.

Puntos:
- **Último respaldo disponible:** Cómo se hará? Cada cuánto se hará? Se hace de acuerdo a tu naturaleza de operación.
- **Análisis y valoración del daño:** Ver que cosa fa










