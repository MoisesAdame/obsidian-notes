---
tags:
---
Date: 2025-02-24 : 14:13
***
## Lenguajes de Desarrollo de Software
- Un lenguaje de programación **nunca puede ser ambiguo**.
- Es la sintaxis que tenemos para que la computadora interpretar el significado de los programas de dicho lenguaje.

### Programa
- Secuencia finita de dígitos y caracteres, legibles por nosotros.
- Se almacenan en archivos de texto en formatos ASCII-UNICODE (porque son universales).

### Función
- Resolver problemas.

### Criterios de Desarrollo
- No hay ningún lenguaje **óptimo**, por ejemplo python, busca que su sintaxis sea simple, mientras que java no, pero buscando que lo que escribas que sea mas seguro.
- Cada lenguaje cumple ciertos criterios.
- Un lenguaje debe ser:
	- Fácil de escribir.
	- Legible.
	- Generalidad.
	- Ortogonalidad o Independencia.
	- Similaridad
	- Simplicidad
	- Expresividad: Darte una forma fácil de expresar algo complejo.
	- Fiabilidad: Resultados siempre sea iguales para el mismo código.
	- Independencia de la máquina: No importa máquina, dar mismo resultado.

## Paradigmas de Programación
### Categorías
#### Lenguajes Imperativos
- Todos los lenguajes que conocemos.
- La mayor parte del sw. comercial

#### Lenguajes Funcionales
- Todo es funciones y recursión.
- No hay variables, no hay objetos.

#### Lenguajes Declarativos
- Encontrar que elementos de un dominio cumplen determinada relación definida sobre dicho dominio.
- Ejemplo es Prolog.

### Puntos en común
- Todos usan funciones.
- Todos tienen asignaciones.

## Entorno de Desarrollo
- Es una aplicación informática con ciertas herramientas que nos facilitan la vida a la hora de programar.
- Pueden estar adaptados para un lenguajes o para muchos lenguajes.

### Componentes de Entorno
- Un IDE.
- Un compilador o intérprete.
- Depurador o debugger. Además de los breakpoints, nos sirve para loggers, que son la alternativa de el **print**.
- Constructor de interfaz gráfica. IGNORAR
- Control de versiones. El mas comun es GIT
	- Main branch: Debe estar protegida. Lo que esta ahí debe funcional al 100%

### Niveles de Entorno
En todos los proyectos debe haber tres entronos:
- Desarrollo: Donde estamos constantemente cambiando cosas.
- Montaje o UAT: Es la pre-producción. Ya terminé, pruébalo.
- Producción: Súbelo.

Para cada nivel, debe haber código y base de datos.

## Plataforma de Desarrollo
### Que es?
- Entorno o ambiente de software común en el cual se implementa la programación de un conjunto de aplicaciones.

### Ejemplos
- iOS, Linux, Windows

### Componentes
- Módulo de captura y comunicación: Para AWS son interfaces web. Cosas como terraform. Puede ser por interfaz o puede ser por comandos.
- Modulo de almacenamiento y procesado. Debe tener bases de datos.
- Modulo de presentación y control. Te deja ver dashboards

