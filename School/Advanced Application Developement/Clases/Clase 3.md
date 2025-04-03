---
tags:
---
Date: 2025-04-02 : 16:05
***
## Módulo AI (Valverde) 
### Otras Especificaciones
#### Función ALBO
Es la anotación que un experto le pone al dato.

#### Modelos de Representación
1. Matemático: Regresión lineal, redes neuronales, máquinas de soporte vectorial. Clasificador es una función de probabilidad. Todo modelo de aprendizaje supervisado tiene dos funciones: La de probabilidad y la de mapeamiento. 
2. Simbólicos: Árbol de decisión, reglas lógicas proposicionales, redes semánticas. No son modelos nuevos, pueden ser de los más antiguos, los mejores son los árboles de decisión. Los árboles de decisión se encargan de reducir la entropía (la medida de desorden), son los mas importantes. Redes semánticas son grafos de conocimiento.
3. Lazy: Son los más pobres en cuestión de lógica, pero los más difíciles de vencer. kNN, raciocinio basado en casos
4. Probabilísticos: Redes Bayesianas, naive bayes, mistura gausiana, modelos ocultos de markov. Estos se usan en ámbitos donde **no podemos fallar**. Su punto débil es que requiere un hmano.

Top 3 algoritmos más importantes: SGBus, Redes neuronales y SVM.

### Paradigmas de Aprendizaje
#### BIAS
Desviación o tendencia para inducir cierto comportamiento

Bias Inductivo: Es la tendencia a privilegiar una hipótesis o un conjunto de hipótesis específicas.

#### Evaluación
Es un proceso que debe ser implementado de forma rígida.

### Pipeline de Proyectos de ML
#### Introducción
Muy similar al de un proyecto normal de software.

Partes:
1. **Project Set Up:** Requisitos basados en datos enfocados a cumplir objetivos de negocio. La parte dos son los modelos, elegir el modelo correcto.
2. **Data Preparation:** 1) Data collection (Es la base de datos) 2) Data cleaning (filtrado de datos y los limpias con algún algoritmo depende de la tarea) 3) Feature engineering (Hoy es el 90% del esfuerzo. Es empaquetar los datos para que el modelo lo consuma.) 4) Split the data (Divides los datos 20% para testear y 80% de entrenamiento, pero hay técnicas para hacerlo.)
3. **Modelado:** Se empieza en paso 2. 2) Entrenar modelos.
4. **Deployment:** 1) Elegir el o los mejores modelos. 3) Mejorar el modelo.

### Natural Language Processing (NLP)
#### Qué es?
Métodos computacionales orientados a entender o generar lenguaje natural.

#### Por qué es difícil?
Porque el texto es ambiguo, hay muchas formas de decir lo mismo, depende del contexto, no hay reglas duras.