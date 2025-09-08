
## Markov Chain
?
- Contains set of states S1, ... , Sn
- Time step
- Probability vector at time k
	- each probability represents probability of being in particular state at time k
	- each probability is >= 0
	- sum of probabilities = 1
- Transition matrix A is symmetric where Aij = probability of moving from state j to state in one time step
	- sum of columns each equate to 1
- Probability at time n is given by A^n * probability at time zero

## Properties / Axioms
?
1. ...
2. ...
3. ...

## Examples
?
- Example 1: ...
‎ 
- Example 2: ...
‎ 
- Example 3: ...

## Non-examples
?
- Non-example 1: ...
- Non-example 2: ...

## Theorems
- A^d is a transition matrix for where d >=1 and the matrix has all positive entries.
	- 1 is eigenvalue of A
	- Any other eigenvalue has absolute value less than 1
	- lim as n --> inf of A^n = probability vector
	- lim n --> inf of probability at time n = probability vector times probability at time 0





#linear-algebra