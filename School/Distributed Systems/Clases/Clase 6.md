---
tags:
---
Date: 2025-04-08 : 16:40
***
## Molina 
### Inter-VLAN Routing
#### Introducción
Para que podamos meter una computadora a la red, necesitamos varias cosas:
- Conexión física.
- IP.
- Máscara.
- Default Gateway.

#### Qué es?
Lo padre de las VLAN's es que al **definirlas** no podemos ver otras.

El problema, es que para que se puedan comunicar, necesito o un **swicth capa 3** o un **router**. Lo cual no es escalable.

Los **switch capa 3** son caros porque nos dan la velocidad de capa 2 en la capa 3. Con prenderlo, hace routeo de VLAN's. Por lo que se puede decir que es **nativo**.

#### Packet Tracer - Configure Router-on-a-Stick Inter-VLAN Routing
Definimos vlans:
`vlan 10`
`vlan 30`

Definimos la interfaz para esas vlans:
`int f0/6`
`switchport mode access`
`switchport access vlan 30`

Ponemos como truncal la interfaz correspondiente:
`switchport mode trunk`

Ponemos interfaces que pasarán por esa truncal:
`switchport trunk allowed vlan 10,30,1`

Guardamos configuración
`copy running-config startup-config`

Ahora nos vamos al **router**. Y ponemos la interfaz lógica de la VLAN
int gigabitEthernet 0/0.10

Para G0/0.10 tenemos 172.17.10.1/25 Hay que definir el tipo de protocolo usado para el multiplexeo en la vlan.
`encapsulation dot1Q 10`
