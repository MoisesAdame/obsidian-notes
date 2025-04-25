---
tags:
---
Date: 2025-04-24 : 16:13
***
## Módulo: Investigación 
### Estructura de Artículo Investigación
#### Abstract
Informa al lector del contenido del artículo de forma resumida.

#### Introducción
- Establece el objetivo de la investigación
- Primer párrafo: Objetivo
- Párrafos intermedios: Estado del arte

#### Metodología
- Describe todos los métodos para obtener los resultados.
- Deben ser los suficientemente detallados para repetir el experimento.

#### Resultados
- Poner lo que obtuve, si decir es "mejor", es "peor", nada de eso.
- Debe contener todo lo que se obtuvo de los métodos.

#### Discusión
- Comparar los resultados que obtuve con los de otra persona.

#### Conclusioón
- Parte 1: Resumimos todo lo que viene en el artículo
- Parte 2: Lo lograste o no.

### Estilo de Escritura
- Siempre en voz pasiva. ("Se encontró que la mayoría de los usuarios presentó un perfil de riesgo menor al 70%")
- Nunca en **primera persona**.

### Citas y Referencias
- Cita Textual: "lo que el autor dijo"\[1]
- Cita Parafraseada: Mis propias palabras.\[1]
- Resultados Obtenidos Durante el Trabajo de Investigación: No se necesita referencia.

### Lectura Crítica de un Artículo de Investigación
#### Relevancia y Originalidad
La pregunta que responde es interesante o relevante

#### Claridad y Calidad
- Es fácil de leer.
- Las conclusiones tienen el soporte adecuado.

#### Presentación de Datos
- Las tablas y figuras son relevantes. No poner por poner tablas o gráficas, solo poner las que voy a mencionar.

#### Fallas en el Artículo
- Las conclusiones contradicen a la evidencia.
- La metodología no va a corde con la investigación.

#### Investigación Replicable
Puedo volver a hacer el experimento.

#### Investigación robusta
Debe contener información suficiente para establecer conclusiones confiables.

## Módulo: Estadística
### Distribuciones Continuas
#### Distribución Uniforme
Función de densidad:
$$ 
f(x) =
     \begin{cases}
       \frac{1}{b - a} &\text{si}& a \leq x \leq b \\
       0 &\text{otro caso} \\
     \end{cases}
$$

Función acumulada:
$$ 
F(x) =
     \begin{cases}
       0 &\text{si}& x < a \\
       \frac{x-a}{b-1} & \text{si} & a \leq x < b \\
       1 &\text{si}& x \geq b\\
     \end{cases}
$$
Media
$$
E(X) = \int_{-\infty}^{\infty}xf(x)dx = \int_{a}^{b} \frac{x}{b-a}dx = \frac{a+b}{2}
$$

Varianza
$$
Var(X) = E(X^{2}) - E(X)^{2} = \int_{-\infty}^{\infty}x^{2}f(x)dx - E(X) = \int_{a}^{b}x^{2}f(x)dx - E(X) = \frac{(b - a)^{2}}{12}
$$

Cuando usar? 

#### Distibución Exponencial Negativa
Función de densidad:
$$ 
f(x) =
     \begin{cases}
       \lambda e^{-\lambda x} & x \geq 0 \\
       0 &\text{otro caso} \\
     \end{cases}
$$

Función acumulada:
$$ 
F(x) =
     \begin{cases}
       1 - e^{\lambda x} & \text{si} & x \geq 0\\
       0 & \text{si} & x < 0 \\
     \end{cases}
$$

#### Distribución Gamma
