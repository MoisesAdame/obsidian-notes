---
tags:
  - ceneval
---
Date: 2025-02-17 : 14:22
***
## Diseño y Arquitectura
### Arquitectura de Software
- Arquitecto hace casas. Pero para eso **que necesita planear** checando materiales, zona, cosas sobre servicios.
- La arquitectura nos da **diferentes formas de ver** un mismo producto. Con el software es lo mismo
- Riesgo es la probabilidad de que algo que **afecte** al proyecto pase. Hay riesgos *positivos* y *negativos*.
- Un riesgo lo podemos manejar de varias formas:
	- Transferir: Con un seguro. Outsourcear.
	- Mitigar
	- Aprovechar

### Stakeholders
- Desde developers hasta clientes.
- Los suppliers también son stakeholders como AWS, Oracle, Google. No siempre **participan activamente**.

### Problemas
- Cómo saber cuál tecnología usar? Conocimiento. Necesidades del proyecto.

### Software Design Description
- Son un conjunto de **artefactos** (diagramas, documentos, entregables) que documentan la arquitectura.
- **No es posible** capturar toda la arquitectura en un solo artefacto.
- Según la persona, es el artefacto.

### Arquitectural Views
- Son representaciones de 1 o más aspectos estructurales de nuestro software.
- Se llaman 4 + 1.
- Al desarrollar una vista hay que ser claro en los detalles, por eso se **inventó UML**.
- Puntos de Vista:
	- Contexto: Relación entre ambiente
	- Funcional: Que tiene que hacer.
	- Información: Como se va a guardar, administrar, la información.
	- Concurrencia: Que partes del sistema pueden ejecutarse de forma **paralela**.
	- Development: Funciones, patrones de diseño, buenas prácticas, etc. Que frameworks, estándares, nombre de variables
	- Deployment: Es base de datos, servers, etc.
	- Operacional: Cosas como soporte y así.
- Perspectivas: Colección de actividades, tácticas y lineamientos que se usan para asegurar que un sistema exhibe un conjunto de propiedades de calidad que requieren considerarse de forma transversal a través de varias vistas del sistema. Al final sirve para **asegurar la calidad**.
- Asegurar la calidad sirve para evitar **desviaciones** a la hora de hacer tu software. Esto sirve para evitar **perder dinero**.

### Catálogo
- Accesidbilidad: Para gente con discapacidades.
- Evolución: Flexible a cambio.
- Internacionalización: Diferentes lenguajes.
- Location: Donde estas (cosas como huso horario). 
- Performance y escalabilidad :: Que tanto tarda.
- Seguridad :: Quien puede hacer que (roles y perfiles). No todo es **encriptar**.

## Patrones de Diseño
### Introducción
- Sirven para **evitar** repetir código. Se llega a ellos mediante la iteración.
- Son formas **comunes** de resolver problemas **comunes**.
- Una especie de **template** para resolver problemas.
- Definen **lenguaje común**, en vez de echar un choro.
- Ahorra tiempo, dan calidad

### Historia
- Erich Game, Richard Helm, Ralph Johnson y John Vlissides son la **Gang of Four**.

### Clasificación
- Hay 3 tipos: Creacionales, estructurales y de comportamiento











