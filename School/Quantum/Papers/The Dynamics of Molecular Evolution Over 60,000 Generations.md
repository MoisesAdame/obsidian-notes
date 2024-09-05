---
tags:
  - paper
  - biology
  - evolutionary-biology
---
Date: 2024-09-03 : 17:05
***
## Article's Information
**DOI:** doi:10.1038/nature24287
**Link:** [Click Here!](http://www.nature.com/doifinder/10.1038/nature24287)

## Abstract
**What is the problem?**
	It is difficult to observe the dynamics of mutations in genomes in a long term.

**What was done?**
	Analyze the dynamics of molecular evolution in **12** populations of E. coli, using their whole genome sequenced every **500** gen during **60,000** gen.

**What was found?**
- Rate of **fitness gain** declines over time.
- Molecular evolution has signatures of **rapid adaptation**.
- Interaction between ecological and evolutionary processes play an important role.
- Targets of natural selection **change** over time.

## Introduction
### Generalities
Research analyzed in the paper suggests that the dynamics of **evolutionary adaptations** are influenced by forces like *rapid adaptation*, *competition between mutation*, *diminishing-returns epistasis* (when the benefit of a beneficial mutation decreases in a relatively fit genotype) and *extensive genetic parallelism*. But this can be due, the short time of the analyzed research.

To resolve these questions they analyzed the **Long Term Evolution Experiment (LTEE)**, which shows that:
- Competitive fitness increases.
- Rate of improvement decreases.
- Fitness gains are accompanied by accumulation of mutations.

### Reconstructing the Molecular Fossil Record
They used a method that only detects mutations if they have a frequency of over **10% in the same place**, finding point mutations and indels.

Using the **total derived allele frequency** they analyzed the rate of accumulated mutations over time $M_{p}(t) = \sum f_{p,m}(t)$. Where $m$ are the mutations, $p$ is the population.

When seeing $M_{p}(t)$ vs. $t$, six populations jumped a lot, which meat they were **mutators**. The **non-mutators** had a falling rate of molecular evolution going from 20 mutations to 10.

### Emergence of Quasi-Stable Coexistence
The **allele frequency trajectory** (allele frequency vs. generation) gives information about selective forces.

Traditionally a single **driver mutation** (gives growth advantage), should fix. In contrast we have many and this can be due to **clonal interference** (multiple mutations that lead to competition). In general, models say that just one lineage must win.

To test this, they used a **Hidden Markov Model** (HMM) to estimate the fixation time. Some populations resemble $M_{p}(t)$, but others segregate in **clades** (organisms or cells that share a common ancestor).

In fact **9 of the 12 populations** have clades. This clades show accumulation of fixations, even when population-wide fixation events have ceased.

This cannot be explained by **clonal interference**, but rather by a **long term coexistence**.

### Dynamics and Fates of New Mutations
They analyzed clade dynamics using the HMM only for basal clades in non-mutator populations. After calculating the **number of fixed mutations**, they found out that it was consistent with $M_{p}(t)$.

When analyzing **transit times** (the time from when a mutation occurs to when it is fixed), we see that they can be low in the first and last generations, despite the **declining rate of fitness**.

Other mutations have high frequencies before getting extinct. To estimate this, they estimated the fixation *probability of a mutation* as a function of its *frequency*. Without clonal interference, they should fix in their clade with a probability of 100%, but this does not happen, meaning that after a lot of generations **clonal interference is still strong**.

### Parallelism at the Genetic Level
Mutators are more prone to **missense mutations** (change amino acid), while non-mutators are more prone to **structural variation (SV)** (genetic variation that involves large segments of DNA, typically more than 50 base pairs).

In non-mutators the **non synonymous to synonymous rate ($\frac{dN}{dS} > 1$)**, whcih means mutations are adaptive. While on mutators $\frac{dN}{dS} \leq 1$, which means that mutations are passenger.

To address **parallel genetic changes**, they used the **effective multiplicity ($m_{i}$)** (the observed number of non-synonymous changes, normalized by gene length.). Showing that there is a correlation with fixation probability in **non-mutators**, but there is not in mutators. Showing that selection plays a high role, but there is still a lot of stochastic processes.

### Signatures of Epistasis and Historical Contingency
#### Definitions
- Epistasis: The effect of a mutation, depends on other mutations.
- Historical contingency: The evolutive outcome, depends on the path/history.

#### Text
Mutation in some genes occurs in a **non-random way**. Some appear in the first generations more often, some appear in latter generations more often.

When all the population has the mutation of a beneficial gene, it gets reduced.

Weak genes are outcompeted by stringer genes.

**Under-dispersed genes** (close to each other in time), are candidates for historical contingency.

For instance **under-dispersion** is bigger when genes appear initially, while **over-dispersion** is lower, when genes appear later.

Thus, **new routes for adaptation are opened by earlier mutations**.

## Discussion
- The targets of selection shift over time. This is for factors as:
	- Ecological interactions.
	- Changing genetic backgrounds.
- Results show that adaptation to a *fixed environment* in a *long-term* has plenty of dynamism.
- 

















































