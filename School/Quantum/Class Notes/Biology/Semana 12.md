---
tags:
---
Date: 2024-10-19 : 20:39
***
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

#### Alineación para cepas de ERY
FASTA del gen rpIV cepa silvestre: [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1?report=fasta&from=1863877&to=1864230)
Alineaciones obtenidas, [aquí](https://trace.ncbi.nlm.nih.gov/Traces/sra-cl-be/sra_web?cmd=screen&run=SRR10584520&seqid=NC_004461.1&range=1863877-1864230&output=fasta&src=SRR10584520&local=undefined&max_lines=133333)

#### Alineación para cepas AMY / GEN y NEO
FASTA del gen fusA cepa silvestre: [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1?report=fasta&from=310737&to=312818) en rango: 310737-312818

#### Alineación para cepas TET
Para encontrar el gen Se utilizó la página [UniPot](https://www.uniprot.org/uniprotkb/A0A0H2VE12/entry). Because no information about the position of the gene was found, I decided to input the UniProt gene identifier A0A0H2VE12 in the NCBI gene search engine, but it was only found in the S. epidermidis ATCC 14990. So, to find any similarities with the strain ATCC 12228, a BLASTn alinesxdxation was performed, which lead to the range 73390-75798, where the gene **SE_RS00345** was found, whose old_locus_tag was **SE0075**.

FASTA del gen SE0075 cepa silvestre: [aquí](https://www.ncbi.nlm.nih.gov/nuccore/NC_004461.1?report=fasta&from=73390&to=75798) en rango: 73390-75798





