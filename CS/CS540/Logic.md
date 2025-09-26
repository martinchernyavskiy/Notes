*Important in the AI field, language of knowledge representation, databases, etc.*

## Symbolic vs. Connectionist 
?
- Connectionist (showcases relations through arrows and nodes)
	- Try to represent with vectors and matrices
- Popular in probabilistic models and neural networks
- May allow AI to write formally verifiable proofs
- *Which is the best?*
	- Combination of the two, like in Markov Logic Networks

## Basics of Logic
?
- *Argument*: a set of sentences (premises) + a concluding sentence
- *Validity*: argument is valid iff all premises are true and conclusion is true
- *Soundness*: argument is sound iff valid & premises true
- *Entailment*: when valid argument, premises entail conclusion
<!--SR:!2025-09-29,4,270-->

## Propositional Logic Basics
?
- Sentences, symbols, connectives, parentheses
- P,Q,R atomic sentences
- *Connectives* include (conjunction, disjunction, implication, biconditional, negation)
	- Precedence follows: not --> and --> or --> implies --> equivalence
	- Parentheses when needed

## Sentences & Semantics
?
- *Interpretation*: (True/False in truth table for symbols)
- *Semantics*: Interpretations for which sentences evaluate to true
- *Model*: interpretation for which all sentences are true

## Knowledge Bases
?
- A set of sentences A1 to An
	- Each connected with conjunction
- Model of KB is interpretations for which all sentences are true
- Goal: inference to discover new sentences

## Entailment
?
- If sentence B logically follows from A, then we write A|=B, this is the case where whenever A is true, B is also true

## Inference
?
- Logical inference creates new sentences from a set of sentences in knowledge base
<!--SR:!2025-09-29,4,270-->

## Methods of Inference
?
- *Enumeration*
	- Enumerate all interpretations and look at the truth table
	- 2^n interpretations for n symbols
- *Using Rules*
	- Logical equivalences & (If A then B, A) entails B
- *Resolution*
	- Convert sentences to Conjunctive Normal Form (CNF)
		- Conjunction of clauses where each clause disjunction of literals
	- Use single rune (*resolution*)
		- Selecting 2 clauses where the latter one has a negative of one symbols of the previous clause
		- Divide over the disjunction of two symbols that were part of the previous clauses
	- Given KB, to show that KB entails a sentence Beta, we add negative of Beta to KB and show that the resolution leads to empty

## First Order Logic (FOL)
?
- Propositional Logic has limitations since we can't say for example that all squares have 4 sides.
	- *We're limited to binary resolutions*
- *FOL* is more expressive logic, works over facts, objects, 