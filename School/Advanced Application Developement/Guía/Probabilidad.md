---
tags:
---
Date: 2025-04-21 : 09:53
***
## Teoría de la Probabilidad 
### Definiciones Básicas
#Q  #AOSR/7f48v
- **Probabilidad** nos permite... que tan... en un... :: Determinar, posible es algo, entorno. #AOSR/7f48v/s/3qn0
- **Variables independientes** son los valores que :: No dependen de otro. #AOSR/7f48v/s/5qci
- **Variables dependientes** son valores que son... por... :: Afectados, otros valores. #AOSR/7f48v/s/69da
- **Muestreo** proceso de obtener un conjunto de... de una... :: Observaciones, población. #AOSR/7f48v/s/5mkq
- **Espacio muestra** es el conjunto... de todos los posibles... de una... :: $S$, eventos, medición.

### Variables Aleatorias
#Q  #AOSR/2hoou
- Define una **variable aleatoria** de manera formal :: Sea $S$ un espacio muestral sobre el cual se encuentra definida una función de probabilidad. Sea $X$ una función de valor real definida sobre $S$ tal que transforme los resultados de $S$ en una cantidad numérica. Una variable $X$ es una variable aleatoria si el valor que asume, de acuerdo con el resultado de un experimento, es un evento aleatorio. #AOSR/2hoou/s/6qnr

#### Variables Aleatorias Discretas
#Q  #AOSR/6eako
- Define una **variable aleatoria discreta** :: Sea $X$ una variable aleatoria. Si el número de valores de $X$ es *finito* o *infinitamente contable* se dice que $X$ es una variable aleatoria discreta. #AOSR/6eako/s/2nuu
- Condiciones para una distribución discreta de probabilidad :: a) $0 \leq p(X) \leq 1$ b) $\sum_{i = 1}^{n} p(X = x_{i}) = 1$ #AOSR/6eako/s/qnum

#### Variables Aleatorias Continuas
#Q 
- Definición de **variable aleatoria** :: Sea $X$ una variable aleatoria. Si los valores de $X$ pueden asumir una infinidad de valores que corresponden a los *puntos en un intervalo de la recta*.
- Condiciones para una distribución aleatoria de probabilidad :: a) $f(x) \geq 0, \forall x \in \mathbb{R}$. b) $\int_{\mathbb{R}}f(x)dx = 1$. c) $f(x) = 0, \text{si } x \not\in \mathbb{R}$

### Funciones Importantes
#### Probability Density Function
#Q
- **Definición (conjuntos)** para una pdf de $X$ :: $f_{X}: \mathbb{R} \to [0, \infty)$
- Las **2 propiedades** que debe cumplir son :: Normalización y no negatividad.

#### Cumulative Density Function
#Q 
- **Definición (conjuntos)** para una cdf de $X$ :: $F_{X}(x) : \mathbb{R} \to [0, 1]$
- **Definición (continua)** para una cdf de $X$ :: $F_{X}(x) = \int_{-\infty}^{x}f_{X}(x)dx$
- **Definición (discreta)** para una cdf de $X$ :: $F_{X}(x) = \sum_{x_{i} \leq x} p(x_{i})$
- Sus **3 propiedades** son :: a) Es *creciente* por lo que si $a < b$ entonces $F(a) \leq F(b)$ b) $\lim_{ x \to \infty } F(x) = 1$ c) $\lim_{ x \to -\infty } F(x) = 0$

## Histogramas, Función Generadora de Momentos y Factores de Forma
### Definiciones
#Q 
- **Distribución** es la... o... en que se acomodan los.. o sus... :: Forma, patrón, datos, probabilidades.
- **Media** es el :: Promedio.
- **Moda** es el valor :: Más repetido.
- **Mediana** es el valor :: Que está en el centro.
- **Varianza** es que tanto los valores :: Varían de la media.
- **Desviación estándar** es la... usa las mismas unidades que los datos... por lo que es mas... :: Raíz cuadrada de la varianza, originales, fácil de interpretar.

### Fórmulas Importantes
#Q 
- Varianza (poblacional) :: $\sigma^{2} = \frac{1}{N} \sum_{i = 1}^{N}(x_{i} - \mu)^{2}$
- Desviación estándar (poblacional) :: $\sigma = \sqrt{ \sigma^{2} }$
- Media (poblacional) :: $\mu = \frac{1}{N} \sum_{i = 1}^{N}x_{i}$
- Varianza (muestral) :: $s^{2} = \frac{1}{n - 1} \sum_{i = 1}^{n}(x_{i} - \bar{x})^{2}$
- Desviación estándar (muestral) :: $s = \sqrt{ s^{2} }$
- Media (muestral) :: $\bar{x} = \frac{1}{n} \sum_{i = 1}^{n}x_{i}$
- Rango :: $max\{ x \} - min \{ x \}$

### Valor Esperado
#Q 
- Fórmula (Discreta) :: $E(X^{n}) = \sum_{\forall i} x_{i}^{n} P(X = x_{i})$
- Fórmula (Continua) :: $E(X^{n}) = \int_{-\infty}^{\infty}x^{n}f(x)dx$
- Varianza :: $V(X) = E\left[ x \right]$


## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Advanced Application Developement/Guía/Probabilidad.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```