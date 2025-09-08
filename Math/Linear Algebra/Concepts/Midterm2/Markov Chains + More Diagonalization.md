
## Markov Chain
?
- Contains set of states S1, ... , Sn
- Time step
- Probability vector at time k
	- each probability represents probability of being in particular state at time k
	- each probability is >= 0
	- sum of probabilities = 1
- Transition matrix A is a square matrix where Aij = probability of moving from state j to state i in one time step
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
		- det(A - tIn) = det(A^t - tIn)
		- set w (1, ..., 1) and note that each row of A^t sums to 1
		- multiplying A^t by w we have a1 + ... an = w
		- So 1 is eigenvalue of A^t with eigenvector w
	- Any other eigenvalue has absolute value less than 1
		- Let c be an eigenvalue of A such that it is not equal to 1.
		- Then the abs of it is less than 1
		- A^t v = cv and v != 0
		- Let absolute value of vk be the max of the abs of vj
		- Then (A^tv)_k = 
	- lim as n --> inf of A^n = probability vector
	- lim n --> inf of probability at time n = probability vector times probability at time 0





#linear-algebra