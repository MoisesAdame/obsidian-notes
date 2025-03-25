---
tags:
---
Date: 2025-03-24 : 16:06
***
## Módulo Reto (Irving)
### Ponderaciones
- CENEVAL, 15%
- Examen Final, 15%
- Actividad Reto, 10%
- Módulos, 10% 10%, 10%

### Fases
#### Fase 1: Análisis de Requerimientos
- Investiga a la empresa (que cosas le han pasado).
- Importante para entender que quiere cliente.
- Discovery Call: Primera vez que conoces al cliente.

### High Level Design
- Muy de alto nivel, no importa que sea poco texto. 
- Agregas algo y se lo enseñas al profe.
- Viene del PMI.
- Todo en inglés.

- **No es necesario llenar todo del HLD.** (Depende de lo que el equipo decida)
- EL HDL se divide en 2: Deployment y Network design.
- No hacer un documento de 50 páginas. Ser claros y sencillos.
- **Historia:** Todas las versiones. Revisiones con profe o entre compañeros.
- **Revisión:** Igual las revisiones con los profes.

1. **Deployment Requirements:** Green Field (Desde cero), brown field (Ya esta funcionando). Deployment timeframes (una especie de GANTT). Bill of Material (De forma simple, decirle cuanto cuesta cada servicio y en total cuanto cuesta todo). Security Requirements (Una contaseña, bla bla bla). Riesgos (Que se caiga toda la red). Exit Criteria (Como saber si se llego al resultado esperado. Tenga un ping de punto A a punto B)
2. **Network Design:**  

## Módulo 2 (Castañeda)
### 2.3 Seguridad
- Mas compleja que aplicar unos cuantos commandos.
- Se **centra principalmente** en las personas y las regulaciones.

## Generalidades
- Mientras mas cerca de los equipos, menos ancho de banda, porque solo cuando sales es cuando se hace el cuello de botella.
- Entre equipos distintos, cable 1 a 1. 
- En la PC o servers, viene habilitado los puertos por default. En router no.

**Direcciones Públicas:**
Son de uso libre.
- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

**Direcciones Públicas:**
Tienes que utilizar una dada por un **registro internacional**.t

- En la entrada de **router** poner la dirección **192.168.1.0/24**. Desde la **1.1** hasta la **1.254**. La **0 y 255** no se pueden asignar. 
- El **switch** no necesita asignarle ip, porque trabaja con en la capa de las MAC. Por eso tiene interfaces, no puertos como en el router.

- Modo enable: Puedes dejar a gente sin conectividad.
- Para ver interfaces: `show ip interface brief`
- Para configurar interfaz: `interface gigabitEthernet 0/0/0`
- Poner localización ip: `ip address <subred> <mascara>`
- Para guardar config: `shutdown`



















