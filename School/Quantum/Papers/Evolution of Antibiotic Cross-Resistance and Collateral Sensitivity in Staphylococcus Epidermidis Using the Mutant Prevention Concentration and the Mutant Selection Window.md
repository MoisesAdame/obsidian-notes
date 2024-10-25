---
tags:
  - biology
  - mutation
  - paper
  - evolutionary-biology
  - evolution
---
Date: 2024-09-04 : 19:15
***
## Article's Information
**DOI:** 10.1111/eva.12903
**Link:** [Click Here!](https://doi.org/10.1111/eva.12903)

## Abstract
### Definitions
- **Minimum Inhibitory Concentration (MIC):** Lowest concentration of an antibiotic that prevents growth of microorganism.
- **Mutant Prevention Concentration (MPC):** Lowest concentration of an antibiotic that prevents the growth of the first step resistant mutants of a microorganism.
- **Cross-Resistance:** Resisting to one antibiotic, makes organism resisting to another antibiotic.
- **Collateral Sensitivity:** Resisting to one antibiotic, makes organism prone to damages of another antibiotic.

### Key Questions
**What is the problem?**
	Cross-resistance and collateral sensitivity are generally, not measured using MPC, instead they are measured using MIC.

**What was done?**
	Measure MIC and MPC of **14 single drug resistant** strains against **7 antibiotics**.

**What was found?**
- MIC and MPC are **correlated**. Correlation weakens if **cross-resistance** doesn't evolve.
- Using MIC and MPC can allow better prediction of mutations in antibiotic-resistant bacteria.

## 1 Introduction
Recently pathogens are more resistant to antibiotics, having both **cross-resistance** and **collateral sensitivity**. A lot of work has been done correlating this to MIC, but very few to MPC.

MPC has the been correlated with cross-resistance. In fact, **Mutant Selection Window (MSW)** a range that goes like $(MIC, MPC)$, shifts up or down depending the collateral-response. That window is the "moment" when the mutations can occur.

As of right now, we don't know the correlations between MIC and MPC, but they depend on aspects such as the **species** and the **type of antibiotic**.

There are different types of antibiotics, if they are the same type, **cross-resistance** tends to appear. For instance, similar **mechanism of action** means cross-resistance. But there are *exceptions*.

What was used:
- **7** antibiotics.
- **5** mechanism of action.
- **2** resistant mutants per antibiotic.

## 2 Materials and Methods
### 2.1 Bacteria and Antibiotics
For each antibiotic they did a process of obtention of two independently mutant batch of bacteria resulting in 14 resistant strains. Then, they evolved **8 strains** in **100 generations** resulting in 56 adapted **resistant** strains.

### 2.2 Liquid MIC
For the **70 resistant strains** they obtained the MIC, basically it was done by pouring different concentrations of antibiotic and finding the one where 95% growth inhibition.

### 2.3 Agar MIC and MPC Assays
#### 2.3.1 Bacterial Preparation
Describes how the bacteria where prepared to be tested.

#### 2.3.2 Determining Agar MIC
There are differences between **liquid MIC** and **agar MIC**. To avoid this, they measured MIC in agar during MPC experiments.

#### 2.3.3 MPC Determination and Analysis
For them, the MPC is the lowest antibiotic concentration where there was no growth across all three replicates. They did this three times resulting in **9 agar plates per drug-strain** combination.

### 2.4 Mutant Selection Window
The MSW was measured in terms of the **parental MIC** value.

### 2.5 Whole-Genome Sequencing
They **sequenced** the parental strain (S. epidermidis ATCC 14990) and all the resistant strains. Then, all the sequences were **aligned** to the reference genome (S. epidermidis ATCC 12228).

### 2.6 Bioinformatics Analysis
Write here.

## 3 Results
### 3.1 Correlated Evolution of the MIC and MPC
In general, all the mutants had an increased **MIC** and **MPC**. In general, when MIC increases, MPC does too.

There were two outcomes:
- If *cross-selection* evolved, the correlation was the same.
- If *collateral sensitivity* evolved, the correlation became **weaker**.

### 3.2 Changes in the Mutant Selection Window
In general, when **resistance evolves** the MSW gets wider. No matter if the resistance is due to evolution of cross-resistance.

Conversely, when **resistance does not evolve** or there is **collateral sensitivity**, the MSW gets narrower or behaves unexpectedly.

### 3.3 MPC Cross-Resistance and Collateral Sensitivity
#### Definitions
- **Cross Resistance:** $max_{\text{父}} < min_{\text{儿}}$
- **Collateral Sensitivity:** $max_{\text{儿}} < min_{\text{父}}$
- **Symmetrical Cross-Resistance(CR)/Collateral Sensitivity(CS):** This can be either for MIC and MPC. If a strain is resistant to antibiotic A and cross-resists antibiotic B, and then different strain is resistant to antibiotic B and cross-resists antibiotic A, thats a symmetrical relation.

Important findings:
- Cross-resistance was seen at least once in every resistant strain.
- Most of the time, both mutant strains had cross resistance.
- The same patters seen in MIC networks, were seen in MPC networks.
- Symmetrical relations are more prevalent in the **MIC** level than in the **MPC**.

### 3.4 Mutations in the Genome
Out of the **13 mutations** found:
- **9 mutations** were missense (a nucleotide change, produces an amino acid change).
- **4 mutations** were other type of mutations.

Depending on the antibiotic, there is a **gene mutation** associated with it, and **resistance** is associated to this type of mutation.

## 4 Discussion
### 4.1 Effects on Resistance on MIC and MPC
We can see that **MIC and MPC are correlated**, but this correlation is subject of the resistance, that is to say, **more resistance, more correlation**.

The MSW shifts to the right and widens when resistance evolves. Because of this **combining drugs** is more effective than increasing a single drug dosage. The latter is because using higher doses, increases the probability for the microorganisms to **mutate and become stronger**.

### 4.2 Cross-Resistance and Collateral Sensitivity at the Network Level
There are more **symmetrical relations** at the MIC leven than at the MPC level. It can be due to the fact that the mutant strains were selected in the **MIC level**, and that an increase in MIC doesn't always mean an increase in MPC.

Due to the fact that the correlation changed, whenever there was a symmetrical relation in the MIC level, if there was no resistance, the MPC didn't behave the same way, so there was no symmetrical relation over there.

Cross-resistance and collateral sensitivity are more important than **drug interactions**. (Because drug interaction changes when the resistance develops, but collateral responses are more stable). And they can be used to **predict evolution**.

### 4.3 Genes Involved in Resistance
A few gene anomalies were found across all the mutant strains:

**TET and OX strains** had identical mutations on gene **SE2021**, the difference is that in the presence of **DOX** MSW of TET got wider and to the right, while the one for OX remained the same.
![[fig4.b.png | 350]]

Although **DOX R1** and **DOX R2** were genetically equal, they showed different **MPC collateral sensitivity** one to **OX** and one to **ERY**, but this can be due to flaws in the liquid MIC.
![[fig5.b.png | 350]]

One last anomaly found was that although the **four strains of GEN and NEO** had different mutations on the same **fusA gene**, they reacted similarly to all the drugs.

### 4.4 Potential Clinical Applications
Usually what a doctor dos is to provide drugs above the MIC, this only creates greater resistance. Thus, it is important to test the behavior of the MSW before giving a treatment.

Some antibiotics have **special behaviors in their MSW**. For example:
- ERY R1
- CPR R2

Use **collateral sensitivity** in a cyclic approach to extend the usefulness of current available antibiotics. But before doing it, it is important considering the MIC vs. MPC correlation, that is not always very predictable.