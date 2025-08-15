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
- Augmented [[Matrix (Matrices)]] w/ elementary row operations that mimic the basic equation operations.
	$m\times(n+1)$ form, right-most being answers to equations.
‎.
- REF of Augmented Matrix
	All zero rows are below all non-zero rows
	The leading entry of each row is to the right of the row above it
‎ .
- RREF of Augmented Matrix
	Leading entries are all 1s
	Leading Entries are only non-zero entry in their columns
<!--SR:!2025-10-14,60,316-->


## Remarks
?
- If leading entry is the rightmost column, then system is inconsistent
.
- If system has columns without leading entries and it's valid REF, then the system has infinitely many solutions.
	- In this case we parameterize the columns with missing leading entry and solve the system.
.
- The rank of a matrix is n-k, where n is number of columns and k is number of columns without a leading entry. If k = 0, there is one solution, if k > 0 and there is a solution, there are inf. many solutions.
<!--SR:!2025-06-29,16,296-->


## Worked-Out Example
?
- Consider an Augmented Matrix in RREF:
$$\begin{pmatrix}
1 & 2 & 0 & 1 & 0 & 2 \\
0 & 0 & 1 & 3 & 0 & 3 \\
0 & 0 & 0 & 0 & 1 & 4
\end{pmatrix}
$$
$\to$$$
\begin{aligned}
x_{1} + 2x_{2} + x_{4} &= 2 \\
x_{3} + 3x_{4} &= 3 \\
x_{5} &= 4
\end{aligned}
$$Use variables corresponding to columns w/out leading entries. Set $x_{2}=t_{1}, x_{4}=t_{2}$
Then:
$E_{1} \to x_{1}=2-2t_{1}-t_{2}$
$E_{2} \to x_{3}=3-3t_{2}$
So the solution set for the system is:
$\{(2-2t_{1}-t_{2}, t_{1}, 3-t_{2}, t_{2}, 4) | t_{1},t_{2} \in R\}$}
<!--SR:!2025-10-21,67,316-->


## Theorems
- [[Basic Operations Don't Change Set of Solutions]]
- [[Every Matrix Can Be Put In RREF]]

#linear-algebra