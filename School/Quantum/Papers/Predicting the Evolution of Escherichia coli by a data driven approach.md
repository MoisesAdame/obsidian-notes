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

## Questions
1. What is the reason for hypermutator cells to appear?



















