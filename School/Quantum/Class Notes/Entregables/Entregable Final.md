---
tags:
---
Date: 2024-11-28 : 15:54
***
## Indice
1. Introducción
2. Desarrollo (Marco Teórico)
	1. Del ADN a los Genes
	2. Mutaciones, tipos, efectos, factores que la generan.
	3. Mecanismos de Reparación de Mutaciones
	4. Bioinformática, Lecturas de Capítulos Seleccionados
	5. Hablar de los Papers Analizados
		1. [[Predicting the Effect of Mutations to Investigate Recent Events of Selection Across 60,472 Escherichia Coli Strains]]
		2. [[Predicting the Evolution of Escherichia coli by a data driven approach]]
		3. [[The Dynamics of Molecular Evolution Over 60,000 Generations]]
		4. [[Evolution of Antibiotic Cross-Resistance and Collateral Sensitivity in Staphylococcus Epidermidis Using the Mutant Prevention Concentration and the Mutant Selection Window]]
3. Resultados
	1. Alineaciones de los Papers (Hablar del proceso, librerías y mostrar resultados)
	2. Lecturas de capítulos seleccionados
4. Discusión

### 1 Introducción
Desde el descubrimiento del Ácido Desoxirribonucléico (ADN) en la década de 1950 por J.D. Watson y F.H.C Crick, este nos ha permitido replantearnos lo que significa estar vivos, siendo una herramienta de gran utilidad para extender y tener una mejor comprensión de ideas tan revolucionarias como las propuestas por Charles Darwin. 

El entendimiento del ADN nos ha permitido como especie modelar procesos biológicos, los cuales, son la base de aplicaciones cuyo rango es extenso que van desde el ámbito médico/biológico, permitiendo el desarrollo de vacunas, pruebas, e incluso terapias, las cuales implican la modificación de su estructura para tratar diferentes tipos de afecciones; hasta el ámbito agrícola permitiendo desarrollar cosechas con mejores propiedades que faciliten su cuidado y apoyen su crecimiento. (Wang & Doudna, 2023)

Pareciera entonces que el ADN es una construcción perfecta y simple, cuya presencia permite que existan todos los tipos de vida conocidos sobre la tierra; pero esto, no es del todo así. A pesar de tener una construcción relativamente sencilla, el ADN y los mecanismos que lo rodean, son extremadamente complejos y robustos, siendo esto último dicho, ya que son capaces de detectar y corregir errores de forma casi perfecta. El hecho de que los mecanismos de corrección de errores sean casi perfectos, aunado a la idea de que cada vez que se unen los ADN's de los progenitores de forma aleatoria, nos permite reconocer la inherente existencia de discrepancias entre los ADN's de un organismo con otro, la cual, según que tan emparentados estos estén, lógicamente se amplía. (Ong & Torres, 2019)

Los conceptos presentados previamente, revelan la formación del ADN de un nuevo organismo, pero como se ha descrito (Urry et al., 2016), debido a que los organismos multicelulares poseen una cantidad enorme de células las cuales están en constante reproducción, el ADN consecuentemente se encuentra todo el tiempo en un proceso donde se copia y se vuelve a reproducir, durante el cual, pueden existir discrepancias, las cuales son causadas por una cantidad innumerable de factores. A estas discrepancias del ADN, les llamamos mutaciones y aunque pueden ser benéficas o imperceptibles, e ocasiones son dañinas y provocan en el organismo que las porta, alteraciones que pueden desembocar en todo tipo de procesos, incluyendo la muerte; siendo tal, el caso del cáncer. (Sadava et al., 2012) Si bien, existe un campo enorme de estudio para los efectos de estas discrepancias, durante esta estancia se buscó el entendimiento de estos procesos mediante el uso de la bioinformática.

### 2 Desarrollo
#### 2.1 Del ADN a los Genes
El Ácido Desoxirribonucléico (ADN) es una molécula que almacena todo el material genético de una célula, se dice que es de doble hélice ya que se conforma por dos hebras que interactúan entre si, las cuales tienen dos partes; primero, una parte de desoxirribosas y segundo, un enlace fosfodiéster, encargado de la unión de las desoxirribosas. Toda la información se encuentra codificada en las bases nitrogenadas las cuales se dividen en dos; purinas (adenina y guanina) y pirimidinas (timina y citosina).

Para comprender como es que el ADN se decodifica, es de gran importancia considerar el Dogma Central de la genética molecular, el cual, en pocas palabras establece que primero, existe un proceso denominado transcripción, encargado de utilizar el ADN para general el Ácido Ribonucléico (ARN), una estructura que costa de una hebra conformada por purinas (adenina y guanina), así como pirimidinas (uracilo y citocina), el cual, es utilizado para un segundo proceso, denominado traducción, que consiste en el agrupamiento de codones (tríos de bases), los cuales, según su orden, son responsables de la generación de aminoácidos, que son los elementos más pequeños, que conforman a una proteína. En total, existen 64 posibles combinaciones de codones, de las cuales 61 son responsables de la codificación de 20 aminoácidos, mientras que las 3 combinaciones restantes, son codones de paro, los cuales, como su nombre lo indica, son los responsables de notificar a los mecanismos responsables, cuando parar el proceso de traducción. 

En muchas ocaciones el ADN y el gen se utilizan de forma errónea como sinónimos, lo cual, se debe al hecho de que el gen es simplemente un fragmento del ADN, el cual al expresarse le da propiedades al organismo. Por su parte, los genes están constituidos por secciones entre las cuales encontramos la región promotora, la región codificante y la región terminadora. Siendo la más importante, la región codificante, ya que es la única que se somete al proceso de transcripción previamente descrito. Es importante mencionar, que esta región en células eucariotas esta constituida por intrones (regiones sin información) y exones (regiones con información), las cuales permiten la existencia de mayor variación genética.

#### 2.2 Mutaciones, Tipos, Efectos y Factores que las Generan
Como ya se mencionó con anterioridad, la mutación es cualquier alteración en la secuencia de ADN de un organismo (Gilchrist, 2024). Por supuesto, debido a que el ADN es una estructura enorme y compleja, se han categorizado distintos tipos de mutaciones, cada una con sus propias características:
- **Mutación Puntual:** Mutación en la que la base original es cambiada por otra.
- **Mutación Sinónima:** Mutaciones que cambian una o varias bases, pero traducción resultan en el mismo aminoácido del codon original.
- **Mutación No Sinónima:** Mutación en la que el cambio de bases, resulta en un aminoácido distinto al original.
- **Transición:** Cambio entre purinas o pirimidinas, entre ellas mismas.
- **Transversión:** Cambio de purina a pirimidina o viceversa.
- **Indels:** Tipo de mutación frecuente durante la duplicación, puede ser ya sea la deleción o la inserción de bases.
- **Mutaciones en el Splicing:** Splicing es el proceso en el que se remueven intrones y se unen los exones. Por su puesto, no es perfecto y cuando existen fallas en el proceso, se generan mutaciones.

Generalmente, asociamos la existencia de mutaciones con efectos negativos, pero este no siempre es el caso. La presencia de las mutaciones puede provocar aspectos tales como:
1. Ganancia de funciones.
2. Pérdida de funciones.
3. Aparición de propiedades nuevas.

Existen una gran variedad de factores que provocan mutaciones, tales como los mostrados a continuación:
1. Errores espontáneos realizados por los mecanismos encargados de la replicación y/o reparación del ADN.
2. Exposición a sustancias nocivas como metales pesados, químicos o tabaco.
3. Exposición a ciertos tipos de radiación, tales como rayos UV, rayos X y rayos gamma.
4. Exposición a ciertos tipos de viruses, los cuales son capaces de insertar su material genético dentro del ADN del receptor.
5. Factores Genómicos, tales como errores en procesos tales como la meiosis o la recombinación.
6. Predisposición genética, es decir, tendencias heredadas para cierto tipo de mutaciones. (Salemi et al., 2009)

#### 2.3 Mecanismos de Reparación de las Mutaciones
El ADN es un constructo que se encuentra en constante replicación y debido a que este proceso es llevado a cabo por la célula, no es perfecto; por ello existen mecanismos de reparación del ADN llevados a cabo por la célula, los cuales son muy robustos y en general permiten que exista una estabilidad genética. A continuación se enlistan y describen algunos de los más importantes:
1. **Reparación por escisión de bases:** Detecta y corrige daños en bases individuales.
2. **Reparación por escisión de nucleótidos:** Detecta y elimina distorsiones presentes en la doble hélice, cortando el fragmento dañado y sintetizando el fragmento nuevo.
3. **Reparación de errores de apareaminto:** Se detectan y corrigen errores de emparejamiento, es decir, bases mal emparejadas.
4. **Reparación por recombinación homóloga:** En ocasiones, la doble cadena sufre rupturas, por lo cual, se utiliza una hebra hermana como molde para sellar el espacio existente.
5. **Reparación por unión de extremos no homólogos:** Repara rupturas de doble cadena cuando no hay un molde disponible. (Alberts et al., 2015)

#### 2.4 Revisión de Capítulos Selectos de Bioinformática
En la primera sección se exploraron los conceptos básicos de la evolución molecular basándose en el ADN y ARN. Así, se describe cómo el ADN almacena la información genética, que se transcribe en ARN para producir proteínas o expresar genes. El ADN está compuesto por segmentos como promotores, potenciadores, intrones y exones. Posee una estructura de desoxirribosa unida por enlaces fosfodiéster, con bases (A, T, G, C) en el ADN y (A, U, G, C) en el ARN. Estas bases forman enlaces de hidrógeno, donde cada tres bases es un codón, los cuales codifican a aminoácidos, los cuales son las estructuras fundamentales de las proteínas.

En la segunda sección, se habló de las bases de datos de secuencias genéticas y las herramientas para buscar similitudes entre ellas, como BLAST. En cuanto a las bases de datos, es importante remarcar el  crecimiento de colaboraciones como INSDC, que abarca a GenBank, EMBL y DDBJ. Además, se describen los tipos de archivos  para almacenamiento de secuencias más comunes como FASTA, NEXUS o PHYLIP. Así como la forma de uso de los números de acceso y versiones de secuencias, específicos para cada base de datos. Por otro lado, se describen algoritmos, como Smith-Waterman para alineamientos locales y se utiliza BLAST para alineamientos múltiples.

Posteriormente, se menciona la importancia de las alineaciones de secuencias para análisis filogenéticos, estas se asume que poseen un mismo origen, aunque existen problemas como repeticiones, sustituciones y gaps, que dificultan su elaboración. Con el tiempo se han desarrollado métodos cada vez más eficaces como la alineación progresiva, iterativa y algoritmos de refinamiento basados en consistencia, utilizados por  herramientas como CLUSTAL, T-COFFEE, MAFFT, y MUSCLE para alinear múltiples secuencias; en algunos algoritmos, se utilizan las matrices PAM y BLOSUM que miden la similitud bioquímica. Mientras que, se propone la edición manual y la comparación de alineaciones usando ALTAVIST y bases de datos de alineaciones como INTERPRO. (Salemi et al., 2009)

Más adelante,  se aborda la heterogeneidad composicional, que describe diferencias en la composición de aspectos cuantificables y su impacto en el análisis filogenético. Se identifican tres tipos de evolución: estacionaria, reversible y homogénea, y se presentan métodos para detectar supuestos violados. Adicionalmente, se introduce SeqVis para analizar secuencias de forma gráfica. También, se mencionan herramientas como CodonExplorer, que permite el análisis de la variabilidad en codones y su relación con la función genética, y UCSC Genome Browser, que ofrece acceso a datos genómicos, herramientas de visualización y comparación de secuencias entre diferentes especies, facilitando estudios tanto evolutivos y como filogenéticos.

Finalmente en las últimas dos secciones se discutieron tanto las distancias genéticas, como modelos de sustitución de nucleótidos,  permitiéndonos comprender la evolución genética a través de mediciones y modelos matemáticos. Este análisis incluye distancias observadas y esperadas, y utiliza el proceso de Markov para modelar las sustituciones nucleotídicas con modelos como JC69 y K80. La heterogeneidad en las tasas de mutación y la saturación de sustituciones ayudan a una buena interpretación de estas distancias, Mientras que, herramientas como Mega4 ayudan a estimar errores estándar y en cuanto a modelos evolutivos, jMODELTEST selecciona el modelo óptimo usando criterios como AIC y BIC. (Posada, 2009)

#### 2.5 Intentos de Predicción de Mutaciones (Revisión de Evolution of Antibiotic Cross-Resistance and Collateral Sensitivity in Staphylococcus Epidermidis Using the Mutant Prevention Concentration and the Mutant Selection Window)
Objetivo del estudio:
La investigación buscaba entender cómo se desarrollan la resistencia cruzada y la sensibilidad colateral a los antibióticos en la bacteria S. epidermidis, causante de infecciones muy resistentes. Con esto en mente, se buscó utilizar valores como la concentración mínima inhibitoria (MIC), concentración de prevención de mutantes (MPC) y la ventana de selección de mutantes (MSW) para predecir y controlar la evolución de las resistencias de la bacteria en cuestión. Así, el estudio buscaba mejorar las estrategias para mitigar la resistencia bacteriana.

Conceptos evaluados y sus definiciones:  
Asimismo, los dos conceptos principales: resistencia cruzada, entendida como la capacidad de un organismo para desarrollar resistencia a un grupo de antibióticos cuya forma de acción es parecida, a pensar de ser expuesta sólo a uno de ellos; mientras que, la sensibilidad colateral es un fenómeno donde la resistencia a un antibiótico hace que la bacteria sea más vulnerable a otros antibióticos. También, se trataron conceptos como la concentración mínima inhibitoria (MIC), entendida como la concentración mínima de un antibiótico necesaria para inhibir el crecimiento bacteriano, concentración de prevención de mutantes (MPC), que es la concentración que evita el crecimiento de mutantes resistentes. Estas dos forman la acotación inferior y superior, respectivamente de la ventana de selección de mutantes (MSW).

Principales resultados:
Se encontró una correlación entre MIC y MPC en las cepas resistentes de S. epidermidis, el problema era que esta disminuye cuando no hay resistencia cruzada. También, se vió que la MSW, se desplazaba de acuerdo con las respuestas colaterales, permitiendo que haya mutaciones. Finalmente, se demostró que ciertas combinaciones de antibióticos pueden provocar sensibilidad colateral, lo que implica que, al diseñar tratamientos, el conocimiento de las MPC puede ayudar a predecir las posibles mutaciones y, por lo tanto, mejorar la eficacia de los tratamientos.

Implicaciones del estudio:
Estos descubrimientos tienen efectos importantes en la medicina, ya que pueden ayudar a desarrollar mejores enfoques para prevenir y controlar la resistencia a los antibióticos. Al usar tanto MIC como MPC en estudios futuros, los investigadores podrían predecir con mayor precisión cómo evolucionarán las bacterias en presencia de distintos antibióticos. Esto también sugiere que el uso de estrategias de tratamiento combinado, basadas en la sensibilidad colateral, podría ser una buena alternativa para evitar el desarrollo de resistencias en ciertas bacterias patógenas.

Aprendizaje y relevancia en formación:
Este estudio me permitió entender a mayor profundidad los mecanismos por los cuales las bacterias desarrollan resistencia a los antibióticos y cómo pueden utilizarse parámetros como la MSW para predecir y mitigar esta resistencia. Estos conceptos, considero que son esenciales el bagaje cultural de profesionales en la microbiología, farmacología y salud pública, ya que permite combatir la resistencia antimicrobiana, sin los efectos secundarios tales como el eventual desarrollo de cepas muy difíciles de tratar.

### 3 Resultados
Para el presente trabajo de investigación, se hizo uso de las cepas de Staphylococus epidermidis adaptadas a la Eritromicina (ERY_R1 y ERY_R2), Gentamicina (GEN_R1 y GEN_R2), Neomicina (NEO_R1 y NEO_R2) y Tetraciclina (TET_R1 y TET_R2). 

Todas cepas previamente mencionadas, fueron alineadas utilizando con el gen de la cepa silvestre (Staphylococcus epidermidis ATCC 12228) listado en la tabla 2 del artículo de investigación, resultando, para la cepa 


### 4 Discusión
Escribe aquí

### 5 Referencias
1. **Watson, J. D., & Crick, F. H. C. (1953).** Molecular structure of nucleic acids: A structure for deoxyribose nucleic acid. _Nature_, _171_ (4356), 737-738. https://doi.org/10.1038/171737a0
2. **Darwin, C. (1859).** _On the origin of species by means of natural selection, or the preservation of favoured races in the struggle for life._ London: John Murray.
3. Wang, J. Y., & Doudna, J. A. (2023). CRISPR technology: A decade of genome editing is only the beginning. _Science_, _379_(6629). https://doi.org/10.1126/science.add8643
4. Ong, J. Y., & Torres, J. Z. (2019). Dissecting the mechanisms of cell division. _The Journal of biological chemistry_, _294_(30), 11382–11390. https://doi.org/10.1074/jbc.AW119.008149
5. Urry, L. A., Cain, M. L., Wasserman, S. A., Reece, J. B., & Minorsky, P. V. (2016). _Campbell Biology, Books a la Carte Edition_. Pearson.
6. Sadava, D. E., Hillis, D. M., Heller, H. C., & Berenbaum, M. (2012). _Life: the Science of Biology_. W. H. Freeman.
7. Salemi, M., Vandamme, A., & Lemey, P. (2009). _The Phylogenetic Handbook: A Practical Approach to Phylogenetic Analysis and Hypothesis Testing_. Cambridge University Press.
8. Gilchrist, D. (2024) _Mutation_, _National Human Genome Research Institute_. Available at: https://www.genome.gov/genetics-glossary/Mutation (Accessed: 02 December 2024).
9. Alberts, B., Johnson, A., Lewis, J., Raff, M., Roberts, K., & Walter, P. (2015). _Molecular biology of the cell_ (6th ed.). Garland Science.
10. Posada, D. (2009). Bioinformatics for DNA sequence analysis. In _Methods in molecular biology_. https://doi.org/10.1007/978-1-59745-251-9
