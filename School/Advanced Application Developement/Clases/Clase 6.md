---
tags:
---
Date: 2025-04-10 : 16:14
***
## Investigación 
Colección para ingeniería: biblioteca.tec.mx/eic

Research Gate: Es buena porque autores suben antes de publicar.

Al menos 15 papers para toda la búsqueda.

Filtrar para quedar entre 5 y 6 ya para la revisión.

## Probabilidad y Estadística
### Métodos Cuantitativos y Simulación
#### Distribuciones Discretas
Veremos: 
- Bernoulli
- Binomial
- Poisson

#### Bernoulli
Solo tiene dos ouptuts: Exito o fracaso.

Cuando analizamos $n$ inetntos de Bernoulli, se llama **proceso de Bernoull**.

Representación:
$$
p(x_{i}) =

     \begin{cases}
       p &\text{si}& x_{i} = 1 \\
       q &\text{si}& x_{i} = 1 \\
     \end{cases}
$$
Media:
$$
E(X_{i}) = 0 \cdot q + 1 \cdot p = p
$$
Varianza:
$$
Var(X_{i}) = (0^{2} \cdot q) + (1^{2} \cdot p) - p^{2} = p(1-p) = pq
$$
#### Generalización de Procesos de Bernoulli: Distribución Binomial
En esta función $k$ son los éxitos
$$
p(X = k) =

     \begin{cases}
       {n \choose k} p^{k}q^{n-k} & \text{si}& k = 0, 1, 2, 3,\dots \\
       0 & \text{en otro lado} \\
     \end{cases}
$$

Como se obtiene $S$ es éxito y $F$ es falla:
$$
P(SSSSS\dots SS FFFFF \dots FF) = p^{k}q^{n-k}
$$

Pero como hay que checarlo para cada combinación hay que agregar el **choose**.

Media:
$$
E(X) = p + p + \cdots + p = np
$$
Varianza:
$$
Var(X) = pq + pq + \cdots + pq
$$

#### Poisson
Se usa cuando eventos que sucenden en un tiempo, área o volumen. 

Representación:
$$
p(X = k) =
\begin{cases} \\
    \frac{\mu^{k} e^{-\mu}}{k!} & x = 0, 1, 2, 3,\dots \\ \\
    0 & \text{en otro lado} \\
\end{cases}
$$

Es importante **notar** que $\mu$ representa el número promedio de resultados por unidad de tiempo o región.

Media y varianza:
$$
Var(X) = E(X) = \mu
$$

