
## Definition
*Equations in the form of:
$$
\left\{
\begin{array}{l}
a_{11}x_{1} + a_{12}x_{2} + \dots + a_{1n}x_{n} = b_{1} \\
\vdots \\
a_{m1}x_{1} + a_{m2}x_{2} + \dots + a_{mn}x_{n} = b_{m}
\end{array}
\right.
$$
Where $(x_{1},x_{2},\dots,x_{n})$ are variables and $(a_{1},a_{2},\dots a_{n})$ are coefficients*

## Strategies
1. Manipulate equations to get to simpler system
2. Get simplest form and read solutions from it
3. Use three basic equation operations:
	1. $E_{i} \leftrightarrow E_{j}$
	2. $E_{i} \leftrightarrow cE_{i}$
	3. $E_{i} \leftrightarrow E_{i} + cE_{j}$

## Representations
?
- Augmented Matrix w/ elementary row operations that mimic the basic equation operations.
	$m\times(n+1)$ form, right-most being answers to equations.
‎.
- REF form of Augmented Matrix
	All zero rows are below all non-zero rows
	The leading entry of each row is to the right of the row above it
‎ .
- RREF form of Augmented Matrix
	Leading entries are all 1s
	Leading Entries are only non-zero entry in their columns

## Remarks
?
- If leading entry is the rightmost column, then system is inconsistent
.
- If system has columns without leading entries and it's valid REF, then the system has infinitely many solutions.
	- In this case we parameterize the columns with missing leading entry and solve the system.

## Worked-Out Example
?
- Non-example 1: ...
- Non-example 2: ...

## Theorems
- [[Basic Operations Don't Change Set of Solutions]]
- [[Every Matrix Can Be Put In RREF]]

## Questions
- ...
- ...
- ...



#linear-algebra