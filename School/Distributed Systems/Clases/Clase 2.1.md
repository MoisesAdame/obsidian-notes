La información que te pasaré a continuación es un documento de notas realizadas durante una entrevista con el dueño de un hospital, el cual, se encuentra en el proceso de abrir nuevas torres médicas y consultorios, para las cuales, necesita una infraestructura de red. Actúa como un analista experto en seguridad informática y utiliza la información de las notas y con ella, realiza un listado de los controles presentes en el estándar ISO/IEC 27002 que le apliquen a la solución y describe brevemente el motivo por el cual dado cada control fue seleccionado.
## Módulo Reto
### Generalidades
- Este proyecto aborda la arquitectura de red en un hospital, destacando la implementación de redes LAN/WAN y servicios distribuidos.

### Características de Negocio
- Hospital que se ha expandido con varias torres grandes y clínicas pequeñas "satélites". 3 hospitales grandes con al menos 5 clínicas pequeñas cada uno como satélites.

### Segmentación
- Centralizar sistema de información, que esta info esté compartida en todos los hospitales.
- Todos los hospitales trabajan con dispositivos médicos que dependen de conexión en internet.

### Prtotocolos y Estándares
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

### Respuestas a Preguntas
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
- Explicación técnica detallada de capa 2 y 3. Escribirla como para su equipo del.

### Core Strategies
#### Topología (Redundancia)
#### Telemedicina
#### IA (Análisis de Datos o Imágenes)
#### Cloud Computing y Almacenamiento
#### Servicio de Virtualización

### Otras Preguntas
#### Infraestructura y Red
1. ¿Qué tipo de dispositivos médicos utilizan actualmente y qué requisitos de conectividad tienen?
2. ¿Qué ancho de banda tienen contratado actualmente y es suficiente para la demanda proyectada?

### Otras otras preguntas
- Qué equipos hay en cada torre? Qué tipos de equipos? Hay dos tipos de quipos administrables(PCS, telefonos servers) y no administrablres (Impresoras, equipos médicos). QUiere que no todo se conecte con todo.
- Prioridad, que necesitaan primero? Disponibilidad al 100% Seguridad al 100%. Luego ver IA. Lo principal es temas de IA.
- Qué tan detallada es la estimación de costos? Solo estimación de servicios. Hardware, almacenamiento, máquina virtual.
- Para el almacenamiento DB. Hacer porpuesta de cuanta info por paciente, cuanto tienen que almacenar y cuanto tiempo.
- Dos especialidades por piso. Hacer estimado con base en eso. No ser tan específicos.
- Todas las personas tienen el mismo ancho de banda. Pero considerar QoS
- Su ISP les da todo el internet que necesitan, no hay problema por eso.
- De IA y analisis de datos? Todo es sus datos, trabajan con cosas como radiografías, TAGS, etc. 
- Que se espera recibir de la IA? Análisis de patrones y diagnosticos. Pueden ser diagnosticos. Pueden ser patrones por edad. Sirve para la toma de decisiones.
- Virtualizacion de maquinas que se virtualiza? CCompus y servers con información sensible. Puede ser servers si lo consideramos. 
- Políticas de seguridad: Nosotros proponer solución de control de acceso a al red. No meterse mucho. Proponer como se manejaría ese sistema de control de acceso.
- Propuesta de VPN, no implementación.