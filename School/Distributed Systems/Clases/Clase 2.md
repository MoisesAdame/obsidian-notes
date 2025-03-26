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

## Módulo 3 (Emmanuel)
### 3.1 Cómputo en la Nuve
#### Definiciones
Definiciones:
- Google: Tipo de **procesamiento** () donde proveedor externo ofrece recursos a través de internet y los comparten personas y organizaciones que desean usarlos o comprarlos.
- Microsoft: Hay una nube **pública** que comparte recursos y ofrece servicios al público a través de internet, una nube privada que no se comparte y ofrece servicios a través de una red interna **privada**.

Que tienen en común ambas def:
- Ambas se manejan por internet.
- Hay un ente que presta **servicios** y otro que **consume**

#### Evolución de ISP
- Como llegamos a esto?

Pasos:
1. Surgen ISP 1.0: Ejemplo prodigy. Ofrecían conectarte al internet. El servicio era te proveo de conectividad.
2. ISP 2.0: Internet por access points.
3. ISP 3.0: Cosas como correo, juegos
4. ISP 4.0: Aprovechar modelo cliente servidor para dar mas servicios. Aqui surgen los correos electrónicos web gratis. Que ganaba haciendolo gratis? Publicidad, datos. Aquí también surge google con el navegador. Google monetiza con marketing GoogleAds
5. Web 2.0: Las posibilidades se multiplican. Tenemos videos, imagenes, compras en línea. Capa de virtualización se hizo necesaria porque todo el tiempo ponian nuevos servers y nuevos software. Ahí, se abre una nueva oportunidad de negocio que es la nube

#### Provider Market
- 1970-1980: Mainframe. La máquina central. El cerebro de la organización.
- 1990: Modelo cliente servidor. SAP, Microsoft, oracle, etc.
- 2000: Yahoo, google. Hadoop es un sw. para big data inventado por yahoo pero no esta basado en investigación de yahoo, sino, sale de un paper GFS, que significa Google File System, Google lo hace privado, pero Yahoo lo hace opensource.
- 2010: The cloud. Se vende una segmentación de usuarios. Eso hace Facebook.

#### Características Clave de la Nube
Cosas que te hacen proveedor cloud:
1. Autoservicio: Tu levantas un proyecto en GCP 
2. Catálogo: Todos los recursos estén catalogados, empaquetados, que te enseñen las diferentes variantes
3. Elasticidad: Debe dar elasticidad de forma rápida. Debe de ayudarte a escalar de forma rápida.
4. Consumo a la Medida: Pagas por el recurso que consumes. Puede ser GB o núcleos. También se cobra por tiempo. Otra forma de que se cobra es por llamada. La desventaja de esto es que **estimar costos** es un reto y en ocasiones **no es rentable**. Es un costo **operativo variable**
5. Confidencialidad/Virtualidad: Mucha seguridad porque almacenan muchos tipos de datos.

#### Modelo de Prestación de Servicios
- Proveedor: Es el dueño, el que administra y el que opera los recursos. Por ello, el dueño define las **reglas del juego**. Su misión es desarrollar y mantener los proces de automatización para prestar sus servicios a consumidores.

#### Ejemplo 1: Caso Nume Pública
1. Azure es el proveedor.
2. Banco contrata servicio de correo electrónico a 100 de sus colaboradores administrado por Microsoft360. Es **nube** por el correo. Es **on-demand** porque paga por 100 colaboradores.

#### Ejemplo 2: Nube privada
Nubes privadas no solo es infra que Google reserva para ti. También es una solución dedicada en una organización donde se conserva este modelo de proveedor y contratante. Si no es así, ya no es nube. Ya que cada quien tiene sus responsabilidades.

#### Ejemplo3: Nube Híbrida
Proveedor es Microsoft, con un modelo público.
Pero Tec quiere mantener su nube privada.

Lo hacen para evitar hacer la inversión que hizo microsoft para cosas como el mail.

Esta estrategia es la más usada hoy end´



