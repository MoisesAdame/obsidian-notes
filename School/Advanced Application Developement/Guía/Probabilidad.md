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
- **Espacio muestra** es el conjunto... de todos los posibles... de una... :: $S$, eventos, medición. #AOSR/7f48v/s/17mr

### Variables Aleatorias
#Q  #AOSR/2hoou
- Define una **variable aleatoria** de manera formal :: Sea $S$ un espacio muestral sobre el cual se encuentra definida una función de probabilidad. Sea $X$ una función de valor real definida sobre $S$ tal que transforme los resultados de $S$ en una cantidad numérica. Una variable $X$ es una variable aleatoria si el valor que asume, de acuerdo con el resultado de un experimento, es un evento aleatorio. #AOSR/2hoou/s/6qnr

#### Variables Aleatorias Discretas
#Q  #AOSR/6eako
- Define una **variable aleatoria discreta** :: Sea $X$ una variable aleatoria. Si el número de valores de $X$ es *finito* o *infinitamente contable* se dice que $X$ es una variable aleatoria discreta. #AOSR/6eako/s/2nuu
- Condiciones para una distribución discreta de probabilidad :: a) $0 \leq p(X) \leq 1$ b) $\sum_{i = 1}^{n} p(X = x_{i}) = 1$ #AOSR/6eako/s/qnum

#### Variables Aleatorias Continuas
#Q  #AOSR/5lhsb
- Definición de **variable aleatoria** :: Sea $X$ una variable aleatoria. Si los valores de $X$ pueden asumir una infinidad de valores que corresponden a los *puntos en un intervalo de la recta*. #AOSR/5lhsb/s/5mvn
- Condiciones para una distribución aleatoria de probabilidad :: a) $f(x) \geq 0, \forall x \in \mathbb{R}$. b) $\int_{\mathbb{R}}f(x)dx = 1$. c) $f(x) = 0, \text{si } x \not\in \mathbb{R}$ #AOSR/5lhsb/s/7onj

### Funciones Importantes
#### Probability Density Function
#Q #AOSR/48i94
- **Definición (conjuntos)** para una pdf de $X$ :: $f_{X}: \mathbb{R} \to [0, \infty)$ #AOSR/48i94/s/z322
- Las **2 propiedades** que debe cumplir son :: Normalización y no negatividad. #AOSR/48i94/s/4j3l

#### Cumulative Density Function
#Q  #AOSR/75evr
- **Definición (conjuntos)** para una cdf de $X$ :: $F_{X}(x) : \mathbb{R} \to [0, 1]$ #AOSR/75evr/s/2bd2
- **Definición (continua)** para una cdf de $X$ :: $F_{X}(x) = \int_{-\infty}^{x}f_{X}(x)dx$ #AOSR/75evr/s/1g08
- **Definición (discreta)** para una cdf de $X$ :: $F_{X}(x) = \sum_{x_{i} \leq x} p(x_{i})$ #AOSR/75evr/s/301p
- Sus **3 propiedades** son :: a) Es *creciente* por lo que si $a < b$ entonces $F(a) \leq F(b)$ b) $\lim_{ x \to \infty } F(x) = 1$ c) $\lim_{ x \to -\infty } F(x) = 0$ #AOSR/75evr/s/6uch

## Histogramas, Función Generadora de Momentos y Factores de Forma
### Definiciones
#Q  #AOSR/1bq25
- **Distribución** es la... o... en que se acomodan los.. o sus... :: Forma, patrón, datos, probabilidades. #AOSR/1bq25/s/7khr
- **Media** es el :: Promedio. #AOSR/1bq25/s/1kl0
- **Moda** es el valor :: Más repetido. #AOSR/1bq25/s/12vb
- **Mediana** es el valor :: Que está en el centro. #AOSR/1bq25/s/z713
- **Varianza** es que tanto los valores :: Varían de la media. #AOSR/1bq25/s/z774
- **Desviación estándar** es la... usa las mismas unidades que los datos... por lo que es mas... :: Raíz cuadrada de la varianza, originales, fácil de interpretar. #AOSR/1bq25/s/2kl9

### Fórmulas Importantes
#Q  #AOSR/1neck
- Varianza (poblacional) :: $\sigma^{2} = \frac{1}{N} \sum_{i = 1}^{N}(x_{i} - \mu)^{2}$ #AOSR/1neck/s/6v08
- Desviación estándar (poblacional) :: $\sigma = \sqrt{ \sigma^{2} }$ #AOSR/1neck/s/5u77
- Media (poblacional) :: $\mu = \frac{1}{N} \sum_{i = 1}^{N}x_{i}$ #AOSR/1neck/s/67ke
- Varianza (muestral) :: $s^{2} = \frac{1}{n - 1} \sum_{i = 1}^{n}(x_{i} - \bar{x})^{2}$ #AOSR/1neck/s/7cpp
- Desviación estándar (muestral) :: $s = \sqrt{ s^{2} }$ #AOSR/1neck/s/10u1
- Media (muestral) :: $\bar{x} = \frac{1}{n} \sum_{i = 1}^{n}x_{i}$ #AOSR/1neck/s/2mle
- Rango :: $max\{ x \} - min \{ x \}$ #AOSR/1neck/s/57fq

### Valor Esperado
#Q  #AOSR/4racl
- Fórmula (Discreta) :: $E(X^{n}) = \sum_{\forall i} x_{i}^{n} P(X = x_{i})$ #AOSR/4racl/s/z115
- Fórmula (Continua) :: $E(X^{n}) = \int_{-\infty}^{\infty}x^{n}f(x)dx$ #AOSR/4racl/s/434i
- Varianza :: $V(X) = E\left[ (X - \mu)^{2} \right] = E\left[ X^{2} \right] - E\left[ X \right]^{2}$  #AOSR/4racl/s/ptv3

### Momentos Alrededor de $\mu$
#Q  #AOSR/3bu2d
- Los momentos de una **variable aleatoria $X$** son los :: Valores esperados para ciertas funciones de $x$. #AOSR/3bu2d/s/22l2
- Sirven para... y... a la.... :: Entender, caracterizar, distribución de probabilidad de $X$. #AOSR/3bu2d/s/6r3i
- **Primer Momento** fórmula..., nombre... :: $E\left[ X \right] = \mu$ #AOSR/3bu2d/s/4aio
- **Segundo Momento** fórmula..., nombre... :: $E\left[ X^{2} \right] = \sigma^{2} + \mu^{2}$ #AOSR/3bu2d/s/1fk0
- **Tercer Momento** fórmula..., relacionado con... :: $E\left[ X^{3} \right]$, asimetría. #AOSR/3bu2d/s/5pa0
- **Cuarto Momento** fórmula..., relacionado con... :: $E\left[ X^{4} \right]$, kurtosis. #AOSR/3bu2d/s/5qis

### Los Dos Tipos de Momentos
#Q  #AOSR/594ot
- Los **2 tipos** son :: Momento alrededor de cero ($\mu'_{r}$) y momento central ($\mu_{r}$). #AOSR/594ot/s/6uk5
- Fórmula de **momento alrededor de cero** :: $\mu'_{r} = E\left[ X^{r} \right]$ #AOSR/594ot/s/61k2
- Fórmula de **momento central** :: $\mu_{r} = E\left[ (X - \mu)^{r} \right] = \sum {r \choose i} \mu^{i}\mu'_{r-i}$ #AOSR/594ot/s/6cu1
- Los **momentos centrales 3ro y 4to** se llaman :: Factores de forma. #AOSR/594ot/s/1tke
- Fórmula del coeficiente de **asimetría** :: $\alpha_{3} = \frac{\mu_{3}}{Var(X)^{3/2}}$ #AOSR/594ot/s/747p
- Rangos de $\alpha_{3}$ :: Inclinada a la *izquierda* si $\alpha_{3} > 0$. *Simétrica* si $\alpha_{3} = 0$. Inclinada a la *derecha* si $\alpha_{3} < 0$ #AOSR/594ot/s/z253
- Fórmula del coeficiente de **kurtósis** :: $\alpha_{4} = \frac{\mu_{4}}{Var(X)^{2}}$ #AOSR/594ot/s/z347
- Rangos de $\alpha_{4}$ :: Si $\alpha_{4} < 3$ es *platicúrtica*. Si $\alpha_{4} > 3$ es *leptocúrtica*. Si $\alpha_{4} \approx 3$ es *mesocúrtica*. #AOSR/594ot/s/7t42

## Distribuciones de Probabilidad
### Distribuciones de Probabilidad Discretas
#### Distribución de Bernoulli
#Q  #AOSR/3uha5
- Un **experimento de Bernoulli** solo tiene :: 2 outputs (éxito y fracaso) #AOSR/3uha5/s/73ul
- Cuando llevamos a cabo **varias veces** un experimento de Bernoulli se llama :: Proceso Bernoulli. #AOSR/3uha5/s/1igh
- Distribución de Bernoulli para un intento :: $$ #AOSR/3uha5/s/6vn1
p(x_{i}) =
     \begin{cases}
       p &\text{si}& x_{i} = 1 \\
       q &\text{si}& x_{i} = 1 \\
     \end{cases}
$$
- Media :: $E(X) = p$. #AOSR/3uha5/s/4rqu
- Varianza :: $\sigma^{2} = pq$ #AOSR/3uha5/s/3hr3

#### Distribución Binomial
#Q  #AOSR/7eq6v
- Sirve para cuando quieres calcular la probabilidad de veces de obtener... en... pero sin tomar en cuenta las... :: Éxitos ($k$), un número de intentos ($n$), repeticiones. #AOSR/7eq6v/s/473q
- Fórmula :: $$ #AOSR/7eq6v/s/2v36
p(X = k) =

     \begin{cases}
       {n \choose k} p^{k}q^{n-k} & \text{si}& k = 0, 1, 2, 3,\dots \\
       0 & \text{en otro lado} \\
     \end{cases}
$$
- Media :: $E(X) = np$
- Varianza :: $Var(X) = npq$






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