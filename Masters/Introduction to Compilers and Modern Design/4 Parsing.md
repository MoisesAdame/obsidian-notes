---
tags:
---
Date: 2025-05-11 : 19:19
***
## 4.1 Overview
#Q 
- An analogy of **parsing** is constructing... out of... :: Sentences, words.
- The form of **valid sentences** in a language is the :: Grammar.
- Context Free Grammars have **2 subsets** :: LL(1) and LR(1) grammars.

## 4.2 Context Free Grammars
#Q 
- Formal definition of a CFG :: $G = (V, \Sigma, R, S)$.
- The $V$ represents the..., they are the... that can occur in the..., they are usually represented as... :: Non-terminals, structures, language, upper-case letters.
- The $\Sigma$ represents the set of... which are the... that can appear in the language :: Terminals, symbols.
- The $R$ represents the... of the grammar and using set notation is represented as... :: Rules, $V \times (V \cup \Sigma)^{*}$.
- The $S$ is the :: Start variable.

#Q
Example grammar of sum of integers
?
$$
P \to E
$$
$$
E \to E + E
$$
$$
E \to identifier
$$
$$
E \to integer
$$

### 4.2.1 Deriving Sentences
#Q 
- A **language** is the set of... that can be described by a given grammar :: Sentences.
- To prove that a **sentence** belongs to a language we must be able to use the... of the grammar in order to achieve it. This process is called... :: Rules, derivation.
- There are **2 types** of derivations... and... :: Top-down derivation, bottom-up derivation.
- In the **top-down derivation** we start from the :: Start symbol.
- In the **bottom-up derivation** we start from the :: Original sentence.

### 4.2.2 Ambiguous Grammar
#Q 
- An ambiguos grammar is one where for a given sentence we have :: **More than one** derivation.

## 4.3 LL(1) Grammars
#Q 
- In order to **ensure** a grammar is LL(1) we first have to remove... then, we remove the... and finally we remove... :: Ambiguity, left recursion, common left prefixes.

### 4.3.1 Eliminating Left Recursion
#Q 
- Left recursion is a rule such that :: $A \to A\alpha$.
- For example the rule $E \to E + T$ is... but changing the rule to $E \to T + E$ although resolves the recursion it changes the... :: Left recursive, grammar.

### 4.3.2 Eliminating Common Left Prefixes
#Q 
- It is used on rules that a common... hand-side :: Left.
- For example a rule that is expressed as $A \to \alpha \beta_{1} | \alpha \beta_{2} | \cdots$ and replace it as :: $A \to \alpha A'$ and $A' \to \beta_{1} | \beta_{2} | \cdots$-

### 4.3.3 First and Follow Sets
#Q 
- In order to have an LL(1) we must have two sets called :: First and follow.
- The set $FIRST(X)$ is the set of... that could appear at the **beginning** of any... of $X$ :: Terminals, derivation.
- The set $FOLLOW(X)$ is the set of... that could occur after any... :: Terminals, derivation.
- Example for a given grammar :: ![[fig4-1.png | 400]]
- 



## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "Masters/Introduction to Compilers and Modern Design/4 Parsing.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```