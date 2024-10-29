---
tags:
---
Date: 2024-10-19 : 20:39
***

## Entregable 0

4. Genetic distances and nucleotide substitution models
	4.1  Introduction
    4.2  Observed and expected distances
    4.3  Number of mutations in a given time interval
    4.4  Nucleotide substitutions as a homogeneous Markov process
	    4.4.1 The Jukes and Cantor (JC69) model 
    4.5 Derivation of Markov Process 
	    4.5.1 Inferring the expected distances
	4.6 Nucleotide substitution models
		4.6.1 Rate heterogeneity among sites
	4.7  Software packages
	4.8  Observed vs. estimated genetic distances: the JC69 model
    4.9  Kimura 2-parameters (K80) and F84 genetic distances
    4.10  More complex models
	    4.10.1 Modeling rate heterogeneity among sites
	4.11  Estimating standard errors using Mega4
	4.12  The problem of substitution saturation
	4.13  Choosing among different evolutionary models
	
5. Selection of Models of DNA Evolution with jMODELTEST
	5.1 Introduction
		5.1.1 Likelihood and Model Fit
		5.1.2 Sequential Likelihood Ratio Tests
		5.1.3 Akaike Information Criterion
		5.1.4 Bayesian Information Criterion
		5.1.5 Performance- Based Selection
		5.1.6 Model Uncertainty
		5.1.7 Model Averaging
		5.1.8 Parameter Importance
6. Single Nucleotide Polymorphisms
7. Simple  Sequence Repeats




## Entregable 2
### Instrucciones
Descargar las secuencias de las bacterias del artículo, y  
generar un alineamiento en donde se puedan identificar mutaciones entre la  
**cepa silvestre** y las **cepas que generaron** resistencia a los antibióticos. El  
alineamiento debe hacerse uno por cada antibiótico listado en la Tabla 2 del  
artículo

### Trabajo Realizado
Link de la secuencia completa de S. epidermidis ATCC 12228, [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1).
Link de las secuencias del paper, [aquí](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJNA593298)


MX: 2281580854
US: +1 8137051488

CHOCOLATE

#### Alineación para cepas de ERY
FASTA del gen rpIV cepa silvestre: [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1?report=fasta&from=1863877&to=1864230)
Alineaciones obtenidas, [aquí](https://trace.ncbi.nlm.nih.gov/Traces/sra-cl-be/sra_web?cmd=screen&run=SRR10584520&seqid=NC_004461.1&range=1863877-1864230&output=fasta&src=SRR10584520&local=undefined&max_lines=133333)

#### Alineación para cepas AMY / GEN y NEO
FASTA del gen fusA cepa silvestre: [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1?report=fasta&from=310737&to=312818) en rango: 310737-312818

En la generación de la secuencia consenso para GEN_R1, se encontró un problema, ya que todas las en el punto 1173, se encontró un agujero, de tal manera que el algoritmo no podía proseguir, por ello, se checó la secuencia referencia y en una secuencia cualquiera se puso en ese punto el nucleotido A.

Lo mismo ocurrio en GEN_R2 en la posición 379, donde se cambió por T

#### Alineación para cepas TET
Para encontrar el gen Se utilizó la página [UniPot](https://www.uniprot.org/uniprotkb/A0A0H2VE12/entry). Because no information about the position of the gene was found, I decided to input the UniProt gene identifier A0A0H2VE12 in the NCBI gene search engine, but it was only found in the S. epidermidis ATCC 14990. So, to find any similarities with the strain ATCC 12228, a BLASTn alinesxdxation was performed, which lead to the range 73390-75798, where the gene **SE_RS00345** was found, whose old_locus_tag was **SE0075**.

FASTA del gen SE0075 cepa silvestre: [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1?report=fasta&from=73390&to=75798) en rango: 73390-75798

The same process for finding gene SE0075 was executed to find gene **SE2021** whose name in the NCBI graphics is **SE_RS09855**.

FASTA del gen SE2021 cepa silvestre: [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1?report=fasta&from=2059306&to=2060985) en rango: 2059306-2060985





