---
tags:
---
Date: 2025-03-25 : 16:46
***
## Módulo Reto
### Generalidades
- Este proyecto aborda la arquitectura de red en un hospital, destacando la implementación de redes LAN/WAN y servicios distribuidos.

### Características de Negocio
- Hospital que se ha expandido con varias torres grandes y clínicas pequeñas "satélites". 3 hospitales grandes con al menos 5 clínicas pequeñas cada uno como satélites.

### Segmentación
- Centralizar sistema de información, que esta info esté compartida en todos los hospitales.
- Todos los hospitales trabajan con dispositivos médicos que dependen de conexión en internet.

### Prtotoclos y Estándares
- Manejo y transmisión de imagen en tiempo real.
- Información de 

### Redundancia y Alta Disponibilidad
- Estrategia de redundancia (por ejemplo si se va la luz que hago.)
- Acceso continuo 24/7.

### Enrutamiento
- Cada hospital es una LAN, explicar como se conectan entre ellos.
- Requerimientos BGP, NAT(nadie pueda ver ips) y ACL (No quiero que todos se puedan comunicar con todos, va a haber doctores, servicios, invitados, etc)

### QoS
- Priorización de trafico, especificamente para **monitores de signos vitales** y **videoconferencias para telemedicina**
- Dar una propuesta de un control centralizado SDN. Para hacer un cambio por ejemplo de clinica satelite en hospital 1, que este sea automatico.

### Virtualización de Servidores
- Dar propuesta de servicio de virtualización.
- Dar estrategia para migrar cosas de una clinica a otra ya sea.
- VDI

### Cloud Computing y Almacenamiento
- Proponer una solución de almacenamiento en red **barata** y que tenga **buen servicio**
- Proponer una **IA**. No puede ser Chat. Que sirva para análisi de datos e identificación de patrones clínicos. Entre más visal mejor
- Telemedicina: Ampliar cobertura sin que pacientes tengan que ir a hospital. En todo México.

### Características de Red
- Confiable
- Segura (que no cualquiera pueda entrar a los servidores, todo sea cifrado)
- Escalable (que no tenga que planear desde cero si tengo que desplegar nuevas clínicas)

### Asistente Virtual



### Preguntas
- Debe haber seguridad en el sistema, porque se esta trabajando con información sensible.
- Nosotros le damos el presupuesto, no hay como tal un límite
- No hay infraestructura preexistente
- 4 pisos por torre.
- 200 personas por torre.
- Clínicas chicas 1 planta de 5 a 6 consultorios con capacidad de 2 administrativos y 1 paciente.
- La implementación esta enfocada en población en general (medicos, pacientes, etc).
- Necesita acceso remoto VPN para poder acceder a info de las bases de datos.
- Toda la comunicación cifrada.
- No puede haber downtime.
- Nos proporcionarán el croquis de los hospitales.
- Ya tienen proveedor de red.
- 
