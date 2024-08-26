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
1. Find mutations in nature. Let $N_{AA}$ be the number of different mutations found.






















## Questions
1. What is a selection test (like GLASS) and what is it used for?
2. In protein evolution, what is essentiality and what is expression level?
3. What is strong purifying selection?
4. What is gene expression level?
5. What is transcription factor?




metodología: diagrama de flujo para contestar la pregunta de cada artículo. 
- Explicar el que no me tocó.
- Prepara diapos para ambos.