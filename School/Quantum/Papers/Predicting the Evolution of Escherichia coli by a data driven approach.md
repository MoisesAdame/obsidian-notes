---
tags:
  - biology
  - mutation
  - evolutionary-biology
---
Date: 2024-08-21 : 02:05
***
## Article's Information
**DOI:** 10.1038/s41467-018-05807-z
**Link:** [Click Here!](https://sci-hub.se/10.1038/s41467-018-05807-z)

## Abstract
**What was done?**
	Analyze and record mutations in different environments.

**What do they manage to prove?**
	How we can train models that predict mutation at a gene level in well-defined environments.

## Introduction
Evolution is not random and has to do with the environment. But at the same time is a mixture of **deterministic** and **stochastic** events. One example of this is **antibiotic resistance**.

**Adaptive Laboratory Evolution (ALE)** is used for this and one of the most used hosts is *E. Coli* due to various reasons. Experiments like ethanol, antibiotics and high acidity environments, prove E. Coli acquired fitness.

Machine Learning has been used for topics like:
- Classification of the binding activity of proteins.
- DNA.
- Guide protein design.
- Gene mutation probability.
- Pleiotropy (the production by a single gene of two or more apparently unrelated effects) in adaptation.

Although there are **mutation databases** that could be used to train models, they are useless because they don't have information such as the environment. If this was done, we could understand better the role of the environment over the mutations and create predictions of a environment, given the mutations.

The study collected a 15,000 mutation events of E. Coli **whole-genome sequencing (WGS)** as well as **metadata**. This was used to train evolution, predicting **gene mutation**, given different environments.

To test their model they evolved 35 lines of E. Coli during 500 generations.

Data showed many things, such as:
- Fixation rate is linear, until the big number of generations creates hypermutator cells.
- Shared mutations across replicates decrease with the number of replicates, the same ratio across any two replicates remain the same, regardless of the number of replicates.
- Higher likelihood to hit DNA-related functions in hypermutators (such as cancer cells).

## Results
### The Mutation Database of E. Coli
A total of **95 papers** were analyzed were they found **15,402 mutation events** grouped in **3819 genomic sites** across **574 evolved genomes**.

Each evolution condition was defined by three attributes:
- Strain
- Medium
- Stress

Of the 15,402 mutation events we found out:
- **57%** were single nucleotide polymorphism
- **26%** were deletions.
- **9%** insertions.
- **8%** amplifications
- **0.02%** inversions.

Spatially we had:
- **80.3%** in mutation sites.
- **19.7** in intergenic regions.

### Mutation Hotspots and Key Targets Across the E. Coli Genetic Landscape
Of the **20 most common mutated genes 12** were related to carbohydrate transport and metabolism.

In **30.9% of the conditions** there was a mutation in the **RNA polymerase (rpboB) subunit**. Although this is common in all evolution experiments.

In **hypermutators** it was found that the most common mutations stayed the same but with a **higher rate**. Additionally **100% had DNA related mutations**, while normal cells had **56% DNA related mutations**.

### Co-Occurring Mutations
To see if there was an overlap in the dependencies among mutations they used a **spectral clustering approach**, which led to **6 clusters**. They found a high number of **membrane proteins** and **sensors for environment conditions** (used for adaptation under pressure).

### Fixation Rate and Number of Generations
If we plot mutations vs. generations the relation is **linear** (with no hypermutators) and **exponential** (with hypermutators).

We can also say that although in normal clones there was a **linear** relation, **fixation rate is not constant**.

It was found that factors like the **strain, stress, medium and generation** contribute to know if the mutation rate is **higher or lower**.

### Mutation-Based Clustering is Informative of the Action Mechanism
When grouping evolutions that had the same **strain** and **medium** the mutation-based clustering has information about the **mechanism of action**.

### Evolutionary Signatures Increase Linearly with Replicate Experiments
To address how predictable evolution is from the perspective of genetic mutations, we evaluated the frequency of mutations. The results showed that **when replicates are few, there are more similarities**, conversely **alternative patterns emerge when the number of replicates increases**.

### A Pattern of Shared Mutations Across Replicates
They analyzed two ratios:
- **Global Overlapping Ratio:** Shared mutations in all clones.
- **Pairwise Overlapping Ratio:** Shared mutations in any two clones with same condition.

Both of them **decreased** with the number of replicates. But the **global overlapping ratio** decreased more, with respect to the **pairwise overlapping ratio**.

### Predicting Evolution Through Data Integration
Using this data an **ensemble predictor** was trained combining outputs of an **Artificial Neural Network (ANN)**, a **Support Vector Machine(SVM)** and a **Naive Bayes (NB)** classifier. 

The **inputs** for the predictor were **medium, strain, generation and stress** while the **output** is the **probability of a genome site is mutated**.

The performance changes depending the **mutation and mutation site** and it is proportional to the **frequency of a genome site being mutated across various culture conditions**.

To **test the predictor** they used a new condition, predicting **34.5% ± 5.7% of the mutation targets** with a **49.2% ± 5.8% precision**.

## Discussion
This was the fist **E. Coli Evolution Database**.

One of the top genes found was **transcription related (rpoB)**, and is important because affects cell metabolism and hundreds of genes positively.

Hypermutators were found to be caused due to mutations in **DNA replication and repair genes**.

A lot of **cross-stress protection** (when adaptation to one stress helps another) was seen. Also, **fitness advantage mutation** was seen until a lot of replicates. The stress an organism is exposed to, creates an **imprint in the genome**.






















## Questions
1. What is the reason for hypermutator cells to appear?



















