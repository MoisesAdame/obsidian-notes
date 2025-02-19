---
tags:
---
Date: 2025-02-19 : 14:26
***
## Modelo de Datos
- Modelos de datos de alto nivel o conceptuales: Hay diagrama entidad relacion y modelo no relacional. En ambos hay entidades (objetos)
- Esquema es tablas columnas y relaciones. Estado es todo eso, pero con datos
### Arquitectura de Esquema Triple
- Nivel Interno: Describe la estructura. Como se va a aguardar datos en memeroia
- Nivel Conceptual: Tablas, columnas, relaciones
- Nivel externo: Cosas como DTO's, 

### Características del enfoque de Base de Datos
- DBMS: En español es SGBD. Es donde entran los query languages.

### Independencia de los datos
- Hay física: 
- Hay lógica

### Lenguajes e Interfaces de Bases de Datos
- Compila el lenguaje y logra darnos un resultado.
- DBA son los comandos. Esto se compila. El administrador de datos almacenados es la parte de indexado.
- Consultas interactivas: Es con interfaz gráfica.
- Precompilador: Son los drivers. Precompila la consulta en el lenguaje del HOST.

### Arquitecturas
- Centralizada: Todo está en un mismo servidor
- Cliente-servidor: Varios servers que consumen entre sí.

### Utilerías
- Cargado: Llenar base de datois
- Respaldo
- Reorganización: Indexado. Consulta más rápido
- Monitoreo de desempeño: Estadísticas de cosas como que query es mejor.

### Clasificación de DB
- Por modelo de datos: De red. De grafos
- Modelo jerárquico: Para big data.
- Modelo orientado a objetos:
- Relacional: MySQL
- Por número de usuario: Todos los que conocemos son multiusuario.
- Distribuido:

## Modelo Entidad Relacion
- Visto en el semestre de Django
- Entidad débil: Entidad cuya key es una foreign key. Si la fuerte muere, la débil también
- Multivaluado: Varios teléfonos.
- Compuesto: Fecha
- Dominio: 

## Modelo relacional
### Reglas de Integridad
- Que debe tener el dato que este adentro. En SQL se llaman **constrainst**

### Reglas de Integridad Referencial y Llaves Foraneas
- Garantiza que las llaves que usemos, existan
- Por defecto: No se pueden meter registros con llaves nulas.
- Se pueden tener llaves foraneas nulas.

### Reglas de Negocio
- Este string debe tener 10 carcateres
- Este int no puede ser mayor a cero.
- 
