---
tags:
---
Date: 2025-04-03 : 16:11
***
## Investigación 
### Metodología PRISMA
#### Qué es?
- Publicada en 2009
- En 2020 se hizo actualización.
- Le da estructura a las revisiones de literatura y estados del ante.
- Se hizo porque antes elegían lo que les interesaba, no **todo lo que existía**.
- Generalmente se orienta a **experimentos médicos**.
- Sirve para sintetizar el estado del arte de un campo para identificar **áreas de investigación**, sugerir mejoras, presentar teorías de comportamiento.

#### Elementos
- Título: Buscar que venga "systematic review".
- Abstract
- Describir la razón por la que se hace
- Describir objetivos: Más particulares que la razón. La razón desmenusada.

## Estadística
### Histogramas, Función Generadora de Momentos
#### Medidas de Tendencia Central
- Mediana: Valor que está en el centro
- Moda: Valor que más se repite.
- Media: El Promedio
- Varianza: Una medida de dispersion. Que tan lejos están los observables del promedio.

$$
\mu = \frac{\sum_{i = 1}^{N}x_{i}}{N}
$$
$$
\sigma^{2} = \frac{\sum_{i = 1}^{N}(x_{i} - \mu)^{2}}{N}
$$
- Rango: $R = max(x) - min(x)$

#### Histograma de Frecuencias Absolutas
Para hacerlo hay que:
1. Determinar el rango.
2. Determinar el número de intervalos. Puede ser con $\sqrt{ N }$. También puede ser con la regla de sturges.

#### Valor Esperado y Varianza
##### Valor esperado
$$
E(X) = \sum_{\forall i}x_{i}p_{i}(x_{i})
$$
##### Varianza
$$
V(X) = E[(X - E(x))^{2}]
$$
$$
V(X) = E(X^{2}) - [E(X)]^{2}
$$

#### Momentos Alrededor de $\mu$
Nos sirven para encontrar los parámetros para construir las **funcionesn de distribución de probabilidad**.

Los momentos de una variable $X$ son los valores esperados (promedio) de ciertas funciones de $x$. 

#### Momentos Alrededor de $\mu = 0$
$$
E[x^{r}] = \sum_{\forall x}x^{r}p(x)
$$
##### Momentos
Primer momento: $E(X) = \mu$
Segundo momento (dispersión): $E(X^{2}) = \sigma^{2} + \mu^{2}$
Tercer momento: $E(X^{3})$
Cuarto momento: $E(X^{4})$

#### Tirar Dos Dados: Valor Esperado
Al calcular el valor esperado obtenemos que $E(X) = 7$.

Vemos que el valor esperado del segundo momento es: $E(x^{2}) = 54.8333$

Por ello, la varianza es: $\sigma^{2} = E(x^{2}) - [\mu]^{2} = 5.8333$

#### Asimetría $\alpha_{3}$
Nos dice hacia donde va el sesgo o la asimetría.
$$
\alpha_{3} = \frac{\mu_{3}}{[var(X)]^{3/2}}, \mu_{3} = \mu'_{3} - 3\mu \mu'_{2} + 2\mu^{3}
$$
Donde:
$$
\mu'_{3} = E(X^{3}) = \sum_{\forall i}x_{i}^{3}p(x_{i})
$$

#### Curtosis $\alpha_{4}$
Es que tan achatada o no está la función
$$
\alpha_{4} = \frac{\mu_{4}}{[var(X)]^{2}}, \mu_{4} = \mu'_{4} - 4\mu \mu'_{3}+6\mu^{2}\mu'_{2}-3\mu^{4}
$$
