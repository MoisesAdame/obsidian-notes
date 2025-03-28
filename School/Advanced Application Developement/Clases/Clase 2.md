---
tags:
---
Date: 2025-03-27 : 16:14
***
## Metodología de la Investigación 
### Qué es la metodologia de investigación?
El diseño de un estudio/proyecto para asegurar quemlos resultados son válidos, confiables y cumplen metas objetivos y responden a las preguntan de investigación.

La metodología determina cosas como:
- Tipos de datos que analizaremos
- De donde salen los daos
- Cómo recolectar datos
- Cómo analizarlos.

Hay que justificar **porqué seguimos una metodología** y **cómo se diseñó**.

### Métodos de Investigación
- **Cualitativos:** Info escrita, se enfoca en explorar un tema. Por ejemplo una encuesta. 
- **Cuantitativos:** Cuando haces análisis numérico. Ya no exploras, tienes que hacer una **hipótesis** que tienes que comprobar con tu investigación. Cuántas personas? Qué películas?...
- **Mixtos:** Complementar los métodos entre si. Ver los comentarios de la gente sobre las películas.

### Estrategias de Muestreo
Es como decidir que datos voy a usar. No siempre puedo usar **todos los datos**. Hay que sacar una muestra de esos datos y hay dos formas de sacarlos:
- **Probabilística**: Muestra aleatoria. Minimiza sesgos (que excluye ciertos aspectos). Genera datos más generalizables. En Facebook hay un sesgo de tías y mamás.
- **No probabilística:** No es una muestra aleatoria. Puede tener sesgos. Los resultados no son generalizables.

### Métodos de Recolección de Información
Métodos:
- Entrevistas
- Grupos focales. Tu eliges un grupo específico de personas por su características. Por ejemplo los que se usan para el **bliss point**. Ejemplo de los cheetos.
- Obeservaciones. Medidas de algun tipo.
- Mediciones biofísicas. Muestras de fluidos.
- Registros históricos. Estados contables, calificaciones, precios de acciones en la bolsa.

### Métodos de Análisis de Datos
Cualitativos:
- Por tema. Temas recurrentes (los baños están sucios).
- Análisis de Discurso: Tendencias en el discurso.
- Análisis Narrativo: Interpretación de cosas como entreviostas, monólogos, historias escritas, etc. Muy usado en psicología.
- Análisis Fenomenológico Interpretativo: Como la gente se siente de acuerdo a algo que les pasó. (Kidzania, como te sentiste)
- Análisis Visuales: Videos fotografías y pinturas. (Hotspots turísticos, como identificar movimiento artístico).

Cuantitativos:
- Estatística descriptiva.
- Estadística inferencial.
- Inteligencia artificial.

### Modelo de Investigación en Capas (Onion Model)
- Análisis Longitudinal: A lo largo del tiempo. Ejemplo acciones de las farmacéuticas.

Mientras mas métodos use, mas rica es la investigación, pero a la vez mas difícil de establecer.

- Caso de Estudio: Documentas un caso. Por ejemplo doctor que documenta el uso del veneno de alacrán. 


- Deductivo, veo mis datos y deduzco lo que esta pasando. Tienes una hipótesis.
- Inductivo: Tienes unos datos y a ver que me encuentro.

### Consideraciones Éticas de la Investigación
- Non-maleficence: Que no cause mal.
- Integridad: No usar datos falsos.
- Autonomía: Que no haya conflicto de interés.
- Privacidad: Datos personales (cosas que no pueden ser públicas) Usar los datos para lo que dijiste. 
- Confidencialidad: No divulgar datos.
- Dignidad: Respetar la dignidad de persona. Estudios no invasivos.
- Beneficence: Que nuestros resultados sean una aportación a la sociedad.
- Competencia: Soy lo suficientemente competente para hacer el estiu

## Módulo Leopoldo
### Probabilidad
- Siempre está entre: 0 y 1.
- Hay variables aleatorias de varios tipos: Discretas o continus

### Teoría de la Probabilidad
#### Conceptos
- Probabilidad: Idea que nos permite hacer predicciones que nos permiten decir que tan posible es algo que ocurra o no, enmarcadas por un **espacio muestra**.
- Variables Independientes: Valores que no dependen de otros.
- Variables Dependientes: Se afectan por otros.
- Muestreo: Proceso de obtener un conjunto de observaciones o datos de una muestra.

#### Cálculo de Probabilidades
Probabilidad de dos eventos independientes $p_{1}$ y $p_{2}$
$$
P = p_{1} p_{2}
$$
#### Formalidad
##### Variables Aleatorias
Sea $S$ un **espacio muestral** sobre el cual se encuentra definida un **función de probabilidad**. Y sea $X$ una función de valor real definida sobre $S$ tal que transforme los resultados de $S$ en una cantidad numérica. Una variable $X$ es una **variable aleatoria** si el valor que asume, de acuerdo con el resultado de un experimento, es un evento aleatorio.

Ejemplos:
- $X$ puede ser el número de caras al lanzar monedas.

Hay **dos tipos de variables aleatorias**:
- Para eventos continuos
- Para eventos discretos.

##### Variables Aleatorias Discretas
Sea $X$ una **variable aleatoria**. Si el número de valores de $X$ es finito o infinitamente contable, se dice que $X$ es una variable aleatoria discreta.

**Condiciones**
Estas condiciones se deben respetar desde el punto de vista del **espacio muestra** o de la **variable aleatoria**.
$$
0 \leq p(X) \leq 1
$$
$$
\sum_{i = 1}^{n}(X = x_{i}) = 1
$$
##### Espacio muestra
El conjunto $S$ de todos los posibles eventos de una medición.

##### Variable Observable
Conjunto $X$ de los posibles resultados que puedo observar.

##### Probabilidad
$$
P = \frac{\text{num. de éxitos}}{|S|}
$$
##### Variables Aleatorias Continuas
Sea $X$ una variable aleatoria, si los valores de $X$ pueden asumir infinidad de valores que corresponden a los puntos en un intervalo de recta. 
$$
P(a \leq X \leq b) = \int_{a}^{b}f(x)dx
$$
Donde $f(x)$ es la **probability density function**.

Condiciones:
$$
f(x) \geq 0
$$


$$
\int_{2}^{3} \frac{1}{2}e^{-\frac{x}{2}}dx = e^{-3/2} - e^{-2/2} = \frac{1}{4}(e^{-1} - e^{-1.5}) = 
$$

#### Función de Distribución Acumulada
##### Discreta
$$
F(X) = \sum_{x_{i} \leq z} p(x_{i})
$$

##### Continua
$$
F(X) = \int_{-\infty}^{x}f(t)dt
$$
### Funciones de Distribución
#### Distribución
Es la forma o patrón en la que se acomodan los datos o sus probabilidades.






