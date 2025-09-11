## Random Variables
?
- X: maps random point to real values
- P(X = 3): what is the probability of random variable has having a value of 3
- *Cumulative Distribution Function (CDF)*: $F_{X}(x) := P(X \leq x)$
- *Density / Mass function (PDF)*: $p_{X}(x)$: basically a derivative of CDF
- Expectation (average): $E[X] = \sum_{a}^{}a \times P(x=a)$
- Variance (spread): $Var[X]=E[(X-E[X])^2]$

## Probability
?
- Move from one variable to several
- *Joint distribution*: P(X = a, Y = b)
	- Allows to work with multiple types of uncertainty that correlate with each other
- *Marginal Probability*
	- If X = cold/not cold and we need a = cold, then getting the distribution in just one variable where a = cold is equal to the sum joint distribution for all b random points of Y
- Probability Tables
	- if n variables and k values, we have k to n entries
	- If n and k are too large, this makes it problematic
- *Independence*
	- Random Variables that don't correlate have probability being the product of marginals
	- Requires domain knowledge
- Conditional Probability P(X = a| Y = b) = $\frac{{P(X=a, Y=b)}}{P(Y=b)}$
- Conditional Independence P(X, Y|Z) = P(X|Z)P(Y|Z)
	- Requires Domain Knowledge
- *Chain Rule*
	- P(A1, ..., An) = P(A1)P(A2|A1)...
		- If some conditional independence, we can factor
		- Probabilistic graphical models
- Inference: computeprobability given evidence (conditional probability)
- *Bayes' Rule*
	- $P(A|B) = \frac{P(B|A) \times P(A)}{P(B)}$
	- To proof, we apply chain rule two different times
		- P(A,B) = P(A|B) * P(B) 
				= P(B|A) * P(A)
- *Bayesian Inference*
	- P(H|E) = (P(E|H)P(H))/P(E)
	- Where h is hypothesis, E is evidence
	- P(H): prior, estimate of probability without evidence
	- Likelihood: P(E|H)
	- Posterior: P(H|E): probability of hypothesis given evidence
- *Naive Bayes*
	- Conditional Probability follows bayes rule

## Statistics
?
- Typically we don't know the probabilities that can be seen in bayesian inference
- We try to estimate distribution from samples