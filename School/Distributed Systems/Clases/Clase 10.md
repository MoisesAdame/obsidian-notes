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





