---
tags:
---
Date: 2024-09-23 : 09:07
***
## Section A
### The Phylogenetic Handbook, [[1. Basic Concepts of Molecular Evolution]]
- DNA is a set of ordered nucleotides that store **genetic information**.
- There are many types of **mutations** such as pint, synonymous, synonymous, transition, transversions, indels and splicing.
- Evolution is a combination of stochastic and deterministic events such as **natural selection** and **genetic drift**.
- **Speciation** is when one species divides into two, there are many types.
- To see how related two species are we use phylogenetics, specifically, comparing **morphological characters**. But, sometimes it is not as easy as that, so we have to **align nucleotide/amino-acid sequences**.

## Section B
### The Phylogenetic Handbook, [[2. Sequence Databases and Database Searching]]
- There are many databases, the most prominent are **GenBank**, **EMBL** and **DDBJ**, which have their own identification standards, but, store the same information.
- There are also db's that store different kinds of data such as **protein**, or **specialized** sequences.
- While searching, we can use **text** or input **sequences**. In the latter case, tools like **BLAST** are used to search for similar sequences.
- To input sequences we can use formats such as **FASTA**, **NEXUS**, or even **PHYLIP**.

### Bioinformatics for DNA Sequence Analysis, [[1. Similarity Searching Using Blast]]
- In the world there are three main nucleotide sequence databases NCBI, DDBJ and GenBank, which together are the **International Nucleotide Sequence Database Collaboration (INSDC)**. Of course there are other databases, but they do not have as much quality.
- We can search for a sequence using their specific ID's or by including a sequence segment.
- There have been many methods design to align sequences iot al started with the **dynamic programming** one, and then, they started using models such as **PAM/BLOSUM Matrices**. Finally, ending up with **BLAST**, that has many forms for different uses cases (nucleotide, protein, nucleotide -> protein, protein -> nucleotide, etc.)
- Using BLAST is no simple task, it has many parameters that have to be considered such as *max target sequences*, *expect threshold* (the lower the better), *word size* and even *scoring parameters* (match/mismatch scores).

## Section C
### The Phylogenetic Handbook, [[3. Multiple Sequence Alignment]]
- An alignment is an **homology hypothesis**, while aligning sequences, we encounter many problems such as *repeats*, *substitutions* and *gaps*. Factors that have to be considered to have a decent alignment.
- There have been many approaches for aligning sequences such as the *dot-matrix algorithm*, the *dynamic programming algorithm* and others
- But aligning multiple sequences is a more challenging task, there have been many attempts such as the:
	- **Progressive Alignment:** Used by CLUSTAL.
	- **Consistency-Based Scoring:** Used by T-COFFEE.
	- **Iterative Refinement Methods:** Used by MAFFT, and MUSCLE.
	- **Genetic Algorithms:** Used by SAGA.
	- **Hidden Markov Models:** Comparable to CLUSTAL.
- When selecting a program we have to decide if we want accuracy, or less resource usage. If we want to test which alignment is better, we can use **ALTAVIST**.

### Bioinformatics for DNA Sequence Analysis, [[3. Multiple Alignment of DNA Sequences with MAFFT]]
- MAFFT is a good program for MSA because it uses three strategies. The **progressive method** (uses a guide tree and does it many cycles). The **iterative refinement method** (which defines a score function that has to maximize) and the **consistency based iterative refinement method** (how well the pairwise alignments are).
- Depending on the **number of sequences** or their **length**, we have to specify certain configuration.
- If we have to check if the sequences are **locally** or **globally** alignable, we also have to specify certain configuration.
- Because genomes suffer from **inversions, translocations and duplications**, not every tool works, in this case MAFFT doesn't work. Thus, we have to use tools like **TBA** or **MAUVE**.

## Section D
### Bioinformatics for DNA Sequence Analysis, [[4. SeqVis A Tool for Detecting Compositional Heterogeneity Among Aligned Nucleotide Sequences]]
- 












