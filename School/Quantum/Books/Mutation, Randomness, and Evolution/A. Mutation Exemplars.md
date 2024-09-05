---
tags:
  - mutation
  - nucleotide
  - dna-repair
  - dna-replication
  - computer-mutation
  - human-engineered-mutation
---
Date: 2024-08-11 : 18:18
***
## Four Examples of $C \to T$ Nucleotide Substitution
This examples are:
1. Replication Error
2. Damage and Repair
3. Symbolically via Computer Simulation
4. Result of Human Engineering

## A1. Replication Error
This is all done by the **DNA polymerase** when adding nucleotides, and goes like this:
1. Polymerase goes to the end of the strand.
2. Polymerase adds a complementary unit. This can fail and result in a **misinsertion**.
3. The polymerase **proofreads** and corrects errors. If the error isn't detected, it becomes an **internal mispair**.

When we have an **internal mispair** we have a **premutation**. When we replicate this, we have a **mutation**.

This type of **mutation is rare** because:
1. Misinsertions are rare.
2. Proofreading removes most errors.
3. Mismatch repair, removes most mispairs.

## A2. Error-prone repair of DNA damage
![[figA2.1.png|300]]

Mutations can be caused by **damaging DNA**. One example of this is UVB light, whose photons can be absorbed by the bonds of the Thymine (T) and Cytosine (C). This causes the bonds to break and be different than how they should be, causing what is known as a **pyrimidine dimer**, that can be compared to a  jammed up zipper. Replication causes **mutation**.

Damage from **radiation** or **chemical exposure** can or can't be correctly repaired, the latter causing mutation

**Repairing DNA** is error prone, so it has more errors than normal replication.

How the process works?
1. Damage happens in a C:G base pair (pyrimidine dimer).
2. The damage is found and **excised (extirpado)**.
3. **Repair Polymerase** fills the gap and **ligase** closes the opening.
4. If the **repair synthesis** has error, there is a **mutation**.

## A3. Symbolic Mutation Process in a Computer Program
This is done using **Pseudo Random Number Generator (PRNG)**. Then we define a matrix of $n \times m$, where $n$ is the different types of mutations and $m$ are the possible triplet contexts.

Considering this, we define each mutation as a segment in the number line and use our PRNG to select a place. It is important to say that given a segment $(a, b)$, the value $|b - a| \propto p$, where $p$ is the **probability of the outcome**.

## A4. Human Engineered Mutations
Can be done cheaply using **oligonucleotides**. And the process can make any given DNA strand using the following matrix. The matrix has to be $S_{4 \times n}$, where $S_{ij}$ is the frequency of the nucleotide $i = {A, C, G, T}$ at the position $j$ of the sequence.

Then we can change $ACA \to ATA$, mutating C to A. Then, this genes can be inserted into a host resulting in a **mutant organism**.








