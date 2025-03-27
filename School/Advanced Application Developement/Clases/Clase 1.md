---
tags:
---
Date: 2025-03-26 : 16:12
***
## Módulo 2 (Valverde)
### Máquinas
- Por que tanto miedo a las máquinas? Miedo antiguo de que la creación se rebele contra su creador.
- Agente Autónomo: Algo que hace una única tarea de forma continua.

### Inteligencia Artificial
#### Historia
- Surge en 1956, y es creado por John McCarthy, el le da un orden y acuña el termino AI.
- Pero Alan Turing es el padre de la AI y de la computación.
- McCarthy desde los 50's ya imaginaba que el nombre iba a ser conflictivo.
- Inteligencia artificial no es una inteligencia, porque no se puede equiparar al raciocinio, por lo que no hay que creer que es un mounstro, simple mente **intenta imitar algunas de las tareas asociados con la inteligencia humana**.

#### Cada IA se entrena para realizar una tarea específica.
- Pero por ejemplo, ChatGPT hace varias taareas similares al mismo tiempo.
- Algunas IA's **no son capaces de realizar tareas sencillas** pero **pueden hacer trabajos complicados**.

#### Signos de Inteligencia
- Aprender de la experiencia.
- Encontrar sentido a mensajes ambiguos.
- Responder rapidamente a situaciones diversas.
- Entender e inferir de forma racional.
- Aplicar y adquirir conocimiento nuevo.

#### Organización de la IA
McCahrthy y su equipo organizó la IA en el siguiente cuadrante:
1. Sistemas que actúan como humanos (comportamiento)
2. Sistemas que piensan como humanos (pensamiento y razonamiento)
3. Sistemas que piensan racionalmente (pensamiento y razonamiento)
4. Sistemas que actúan racionalmente (comportamiento)

Chat es tipo 2, pero nos responde como 1.
```mermaid
quadrantChart
    y-axis Comportamiento ---> Pensamiento y Razonamiento
    Campaign A: [0.75, 0.75]
    Campaign B: [0.75, 0.25]
    Campaign C: [0.25, 0.75]
    Campaign D: [0.25, 0.25]
```

#### Tipo 1: IA que Actúa como Humano
- El estudio de como hacer que las computadoras hagan tareas en las cuales hasta el momento el ser humano tiene un mejor desempoeño.
- **El modelo es el hombre:** El objetivo es construir un sistema que se pase por humano.

#### Tipo 2: IA que piensa como humano
- Es como el machine learning.
- El **modelo** es el funcionamiento de la mente, como piensa un humano, como deduce un humano.
- Ejemplo: Redes neuronales, se inspiran en el modelo cognitivo humano.

#### Tipo 3: IA que Piensa Racionalmente
- Las principales IA's que se implementaron fueron en los 70's. Un ejemplo era el sistema MISIN.
- Las leyes del pensamiento racional se basan en lógica.
- La lógica anterior no fue suficiente y por es se creo la **fuzzy logic** que es una lógica de estados, y es multiestados.

#### Tipo 4: IA que actua racionalmente
- Relacionada con conductas inteligentes en artefactos.
- Trae el paradigma del **agente**.

#### Agente
- Definición: Es algo que hace algo.
- Agente racional: Es aquel que actua con el fin de lograr el mejor resultado...
- Russel y Norvig: Todo aquello que percibe su ambiente y que reacciona al ambiente a través de acciones. PEAS

#### Agente Inteligente
Entidad **física o virtual** que posee ciertas características generales:
- Representar el entorno
- Percibir el entorno
- Actua en el entorno
- Puede comunicarse
- Posee objetivos
- Posee recursos propios.

Hacen lo correcto de a cuerdo a sus percepciones.

Es aquel que emprende la mejor acción posible en una situación dada.

#### Sueño de la IA
Que se pueda diseñar agente **inteligente/racional** que opere o actúe en diversos ambientes.

La IA generativa no es la respuesta, es la IA generalista.

#### Sistemas MultiAgentes
Sistemas complejos
- Se descomponen en agentes.

#### Artificial Intelligence
- Area de la Ciencia de Computación creada en 1956

#### ML
- Una subarea de la IA.
- Su objetivo es dado un cierto problema, resolverlo con un agente inteligente y un conjunto de información relacionada a ese problema.
- Machine learning es un agente que se especializa en solucionar un único problema.

#### Deep Learning
- Una de las técnicas mas populares de ML.
- Requiere mucho hardware.
- Objetivo: Usar modelo matemático capaz de manejar muchos parámetros al mismo tiempo para mejorar rendimiento de predicción.

#### Generative AI
- En 2017 google publica el paper de Transformers.
- Los trasnformers se basan en redes neuronales.
- La IA generativa es parte del DeepLearning

## Definición Formal
TPE
- T: Tareas
- E: Experiencia
- P: Evaluación

Un programa de computadora aprende a partir de una experiencia E en relación a una clase de tareas T y medida de evaluación P, si su desempeño en alguna de las tareas de clase T, medido por P, mejora con la experiencia E

Ejemplo Ajedrez:
Un programa que aprende a jugar ajedrez (T) podría mejorar su desempeño medidio ppir ka capacidad de vencer más partidas (P) gracias a la experiencia obtenidad jugando cinsigo mismo o con algunas personas (E)

### Sistemas
#### Experiencia
- Hay dos tipos: Directa e Indirecta
- Indirecta: Las decodificamos a partir de otras fuentes,
- Directo: Aprende directamente de los ejemplos de entrenamiento.

#### Paradigmas de Aprendizaje
- Hay 4: Supervisado, no supervisado, semi-supervisado y por refuerzo
- Supervisado: Es el mas caro pero es el mejor. Usa experiencia directa. Le pone labels a los datos.
- No supervisado: No requiere de etiquetas, pero es limitado. Los mejores algoritmos, son los de clustering, pero su resultado , no es un resultado final, tiene que ser analizado por un especialista.
- Semi Supervidado: Usa técnicas de interpolación. Es bueno para deep learning donde necesito mucha info, pero no puedo clasificarla toda.
- Refuerzo: Premias o lo castigas dependiendo de su resultado.

#### Supervisado
- Los datos tienen dos partes $(x, d)$ usamos x para predecir d.
- El label es la función **albo**.

#### No supervisiado
- Los datos tienen dos partes $(x, ?)$.

#### Otras especificaciones
- Modelo = Algoritmo + Datos + Parámetros + Hyperparametros + Otras consideraciones.
- Función albo, puede ser de varios tipos, según los datos. Binaria o incluso múltiple.

