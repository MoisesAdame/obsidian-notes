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

### Estructurales
- Adapter. Es la parte intermedia entre dos interfaces.
- Flyweight. En vez de muchas instancias, solo es una, y así ahorras memoria.
- Proxy. 

### De Comportamiento
- Observer. Cliente servidor. Cuando cambia algo, avísmae.
- Visitador. A ti ya te visité o no.
- Cadena de Responsabilidad. Tengo varios objetos. Uno acaba, le manda un objeto al siguiente y así poco a poco.
- Iterador. Movernos por elementos de un conjunto, sin exponer la implementación.
- Memento: Regresar al estado anterior del objecto. Undo.
- Strategy. Se usa cuando hay concurrencia o formas de hacer algo. Se elige un diferente algoritmo.

### Antipatrones
- Copy paste programming: No sabes si estas metiendo brechas de seguridad. 
- Clase Dios: Una clase que hace todo.
- Repeat code.
- Código muerto.
- Golden Hammer. A mi me funcionó algo, ya lo quiero hacer en todas partes.

## Diagramas
### Diagrama de Clases
- Cardinalidad: Numeritos

### Diagrama de Objetos
- Instancia de una clase.

### Diagrama de Secuencia.
- Como los objetos se intercambian mensajes a lo largo del tiempo.

### Colaboración
- Que métodos usan los objetos para colaborar entre si.

### Diagrama de Paquetes
- Un paquete son clases que resuelven un problema entre si.

### DIagrama de Subsistemas
- Si hay subsistemas, es como el de paquetes

### Diagrama de Componentes
- Componentes físicos del sistema.
- Servidor, servido de base de datos, etc.
- Cada componente interactúa entre ellos.

### Diagrama de Despliegue
- El que confundimos con la arquitectura.

### Modelo 4 + 1
Tines 4 vistas y una guía o lo que une estas vistas, que es el diagrama de casos de uso.
- Vista física: Diagrama de despliegue.
- Vista de procesos: Diagrama de actividad.

En la actividad, solo hacer uno

### Diagrama de Clases
- Usar la notación del lenguaje que se usará
- Asociación: Relación entre instancias de clases.
- Multiplicidad
- Si asociación tiene atributos, se hace un clase aparte.
- Asosiación reflexiva, es cuando es circular. De ti a ti.
- Agregación es cuando no necesitamos uno sin el otro. Carrito de compras necesita productos. Pero usuario no necesariamente tiene carrito.









