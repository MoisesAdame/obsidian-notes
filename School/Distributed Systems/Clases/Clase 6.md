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

De
