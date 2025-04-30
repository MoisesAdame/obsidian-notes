---
tags:
---
Date: 2025-04-29 : 16:25
***
## Molina 
### Protocolo FHRP
#### Introduccion
Significa: First Hop Redundancy Protocol

No es solo uno, es una gama de protocolos.

Estos protocolos buscan que haya redundancia.

Tenemos varios gateways, pero todos ellos, se representan en grupo como una misma salida lógica.

#### Opciones FHRP
Hay varios protocolos:
- HSRP: Protocolo propietario de cisco.
- GLBP: Equilibra cargas.
- BRRP: Es el protocolo abierto

#### Prioridad e Intento de Prioridad de HSRP
En vez de definir interfaz una física, se juntan varias en una lógica.

De los various routers que forman nuestra red, se elige uno principal (activo) y los demás son secundarios (pasivos).

Se puede elegir de dos formas:
- A mano.
- El que tenga la dirección IP más alta.

También se define el valor de **prioridad**, que es el orden en que los routers deben ser elegidos. Si las prioridades son iguales, se toma la IP más alta. La prioridad va de 0 a 255. La prioridad *default* es 100.

Router es **preenty** cuando se une a un grupo de routers se vuelve a considerar.

#### Comandos
Prender protocolo: `standby version 2`

Definir número de grupo y dirección virtual del gateway: `standby <group-number> ip <virtual-gateway-address>`

Cambiar prioridad de default: `standby <group-number> priority <priority>`

Definir como preempt a ese router: `standby <group-number> preempt`

#### Propagar como ir a internet
Se logra con algo como:

router ospf 10
log-adjacency-changes
network 10.1.1.0 0.0.0.3 area 0
default-information originate

Y en la routing table se ve:
O\*E2 0.0.0.0/0 \[110/1] via 10.1.1.2, 4294967274:4294967239:4294967281, GigabitEthernet0/0

**Mientras routers tengan conectividad a través de protocolo de enrutamiento (e.j. OSPF) HSRP puede seguir sirviendo**.

HSRP se comunica por la red local.

## Módulo: Cloud
### Virtualización
#### VM's
Todo proveedor cloud tiene máquina virtual.

Es una emulación de una máquina física con un sistema operativo.

La diferencia con una computadora normal es que tiene **hypervisor** el cual emula lo que hace el hardware.

El **hypervisor** es una emulación en software de ese control primario de recursos físicos.

La VM descononoce (es **agnóstico**) del hecho de que corre sobre un hypervisor.

Tipos de Hypervisores:
- Bare Metal: Todo recae en el hypervisor. No tienen OS. Son las que usan los proveedores.
- Tipo 2: Las que usamos cuando en local instalamos una VM.

#### Ventajas
Nos permite migrar, instalar, etc sin **downtime**.

Permite escalar

Permite migrar tráfico.

#### 
