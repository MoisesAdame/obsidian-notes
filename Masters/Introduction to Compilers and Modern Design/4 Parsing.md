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
- These types of grammars are :: **Top down grammars** (because we start from the initial symbol)

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

### 4.3.5 Table Driven Parsing
#Q 
- The **LL(1) parse table** is used to determine which... for a combination of... and the next... :: Rule to apply, non-terminal, token.
- To construct the **parse table** we initially use all the symbols in the... and if we encounter an $\epsilon$ we add the... :: FIRST set, symbols in the FOLLOW set.
- For the current example, the **parse table** would end up as :: ![[fig4-2.png | 300]]
- Example algorithm for **int * int** :: ![[fig4-3.png | 300]]

## LR Grammars
#Q 
- They are used for more :: More general purpose programming languages.
- They use... techniques :: Bottom-up.
- LR(1) is a superset of :: LL(1)

### 4.4.1 Shift-Reduce Parsing
#Q 
- LR(1) grammars must be parsed using the :: Shift-reduce technique.
- A **shift** action consumes and puts the... into the... :: Token, stack.
- A **reduce** action applies the... replacing the... into... :: Rules of the grammar, sentential form, non-terminals.
- Example :: ![[fig4-4.png | 300]]

### 4.4.2 The LR(0) Automaton
#Q 
- The **LR(0) Automaton** represents all the possible... that are under consideration by a... :: Rules, shift-reduce parser.
- In the automaton **each box** represents a :: State in the machine.
- The boxes are connected by **transitions** that can apply to both :: Terminals and non-terminals.
- In the rules we add a **dot (.)** that represents the :: Parser's position.
- In the example $E \to E. + T$ we know that $E$ is in the... and $+ T$ is the possible next sequence of :: Stack, tokens.
- Example of automaton :: ![[fig4-5.png | 300]]

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