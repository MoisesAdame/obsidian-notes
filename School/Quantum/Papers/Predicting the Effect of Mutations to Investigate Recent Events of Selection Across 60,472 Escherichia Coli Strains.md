---
tags:
  - biology
---
Date: 2024-08-21 : 03:19
***
## Article's Information
**DOI:** 10.1073/pnas.2304177120
**Link:** [Click Here!]([https://doi.org/10.1073/pnas.2304177120](https://doi.org/10.1073/pnas.2304177120))

## Abstract
**Whats the problem?**
	Because of the lack of genomes, microbial genomics used very few distant genomes that only allowed to see fixed mutations.

**What was done?**
	Apply Gene-Level Amino-acid Score Shift (GLASS) to a dataset of 60,472 E. Coli.

**What was found?**
	In the **short term** essential genes are subject of strong **purifying selection** (remove harmful mutations). While in the **long term**, expression level (how much RNA and proteins they produce) determines the rate of gene evolution.

## Introduction
The fate of a mutation has three outcomes:
- Generally disappear.
- Sometimes, become fixed.
- Persist for intermediate frequencies, for long.

The field that studies these fates is **population genetics**. In the 60s *neutral theory*, proposed that **random drift** (not natural selection), causes most genetic diversity such as *polymorphism* (inside a population) and *divergence* (between species). Proposing too that natural selection **removes harmful mutations**.

Because of the lack of genome studies initially focused on **divergence**, neglecting **polymorphism**. Now we know that polymorphism have different pressures than divergence, some of the being advantageous in a short time.

Detecting **natural selection on polymorphism** doesn't just rely on knowing things like:
- Frequency of mutations.
- Their *synonymous* (don't change the protein sequence) or *non-synonymous* (change the protein sequence) status.

Another alternative is to analyze the effect of mutations in **protein function**. Bioinformatics work has been done being the most successful tool **Direct Coupling Analysis (DCA)** because trough comparison, manages to say if a mutation is harmful, additionally, considering things such as **epistasis** (interaction between amino-acids).

The study uses GLASS, a selection test that uses DCA (for predicting the effect of mutations) for comparing in the absence of natural selection. GLASS also proves that natural selection acts differently depending in the amount of time, for instance:
- **Short Term:** Harmful mutations.
- **Long Term:** Purifying selection and *rate of gene evolution* influenced more by expression levels than by whether the gene is essential. 

## Results
### GLASS: Using Predicted Effect of Mutations to Test for Selection
Generally, selection is studied by comparing synonymous and non-synonymous mutations, assuming that **the more non-synonymous mutations, less fitness**. Also, **the more purifying selection, the fewer remaining non-synonymous mutations**.

In this case, we want to infer the effects of non-synonymous mutations using DCA, a method that assigns scores to mutations giving **high scores** to mutations that **affect the stability and function** of a protein.

The main idea is to **compare DCA distributions** between real and simulated mutations, goes like this:
1. Find mutations in nature. 
2. Let $N_{AA}$ be the number of different mutations found.
3. $N_{AA}$ is a sample of the total number of possible mutations ($19L$).
4. Compute DCA both for $N_{AA}$ and for $19L$.
5. Quantify the shift $S_{obs}$ between $N_{AA}$ and $19L$ distributions. 
	1. If $S_{obs} = 0$, then both distributions are equal.
	2. The higher the $S_{obs}$, the more beneficial mutations are.
6. Compare $S_{obs}$ with shift values in simulated mutations (without selection)

The latter comparison gives us both $\sigma$ and $\mu$ that allow us to compute the GLASS score:
$$
GLASS_{score} = \frac{S_{obs} - \mu}{\sigma}
$$

If the $GLASS_{score}$ approaches zero, means that **simulated and real mutation distributions look the same**. Conversely, means that there is a **higher level of purifying selection**.

### In the Short Term, Essentiality and Expression Level Determine the Intensity of Selection Acting on a Gene
Key concepts:
- **Gene Essentiality:** Genes that are needed for living.
- **Gene Expression Level:** How much a gene is converted into proteins.
- **Nucleotide Diversity:** The average differences in nucleotide sequences between pairs of individuals in a population.

For all the genes found in all the genomes analyzed, they computed the following values:
- **GLASS-P scores:** The scores for the gene polymorphisms.
- **Non-Synonymous to Synonymous Ratio ($\frac{\Pi_{N}}{\Pi_{S}}$)**.
- **Nucleotide Diversities ($\Pi$)**

It was found that GLASS-P scores reflect **recent mutations**, while $\frac{\Pi_{N}}{\Pi_{S}}$ reflect **high-frequency mutations**.

The level of gene expression is *directly proportional* to the **purifying selection** and to the **GLASS-P score**, but *inversely proportional* to $\frac{\Pi_{N}}{\Pi_{S}}$.

Additionally, **GLASS-P scores** predict better **gene essentiality**, compared to $\frac{\Pi_{N}}{\Pi_{S}}$.

### In the Long Term, the Expression Level Drives the Rate at Which a Gene Evolves
A comparison was made between *E. Coli* and *S. Enterica* focusing in genes with at leas **10 fixed mutations during divergence** computing:
- **Non-Synonymous to Synonymous Substitution Rate Ratio ($\frac{d_{N}}{d_{S}}$)**.
- **Nucleotide Substitution Rate ($t$)**
- **GLASS scores (GLASS-D):** Because of Divergence.

It was found that neither **GLASS-D**, nor $t$ relate to **gene essentiality**. But, they relate very good to **CAI** (a method for estimating the level of gene expression).

### Genes That Carry More Deleterious Polymorphisms Are Also More Frequently Lost
There are two types of genes, full-genes and pseudogenes. Pseudogenes are caused by **nonsense mutation**. If we graph pseudogenes/full-genes versus GLASS-P, we find that there is a negative correlation. This means that **lost genes** have 


























## Questions
1. What is a selection test (like GLASS) and what is it used for?
2. In protein evolution, what is essentiality and what is expression level?
3. What is strong purifying selection?
4. What is gene expression level?
5. What is transcription factor?




metodología: diagrama de flujo para contestar la pregunta de cada artículo. 
- Explicar el que no me tocó.
- Prepara diapos para ambos.