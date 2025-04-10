---
tags:
---
Date: 2025-04-09 : 16:14
***
## Valgreen 
Paper Recomendado: Leveraging AI and NLP For Bank Marketing: A systematic Review And Gap Analysis.

Mendeley. Servicio para organizar papers.

Perplexity

### Técnicas Usadas en Análisis de Sentimientos
#### SA in Text
Área de estudio donde se intenta detectar la magnitud de forma cuantitativa de los sentimietos.

Es una tarea de clasificación.

Features son representación numérica de los datos.

#### Técnicas Usadas en Análisis de Sentimientos

## Abdul
### Parsing
#### Gramáticas Independientes de Contexto
Gramática 1 (recursividad izquierda):
1. $A \to Aa$
2. $A \to b$

Gramática 2 (recursividad derecha):
1. $A \to aA$
2. $A \to b$

#### Gramáticas Dependientes de Contexto
Pasan cosas como:
$$
aA \to a
$$

Tienen aplicaciones más en lenguajes naturales.

#### Qué es Parsing?
Encontrar el árbol. Necesitamos encontar cual es la ruta de foma inteligente.

Primero se desarrollo el algoritmo LR. Bottom-Up

Derivaciones:
1. Antes de derivar una $b$: $A \to .b$
2. Después de derivar una $b$: $A \to b.$

#### Ejemplo
Esta gramática es ya no ambigua (solo tiene un árbol de derivación).
1. $E \to E+T$
2. $E \to T$
3. $T \to T*F$
4. $T \to F$
5. $F \to (E)$
6. $F \to id$

Tenemos: $id + id * id * (id + id)$

Reducción (contrario de derivación):
- $F + id * id * (id + id)$
- $F + F * id * (id + id)$
- $T + F * id * (id + id)$
- $E + F * id * (id + id)$
- $E + T * id * (id + id)$
- $E * id * (id + id)$
- $E * F * (id + id)$
- $E * T * (id + id)$

Este no es un algoritmo es la *idea*.






