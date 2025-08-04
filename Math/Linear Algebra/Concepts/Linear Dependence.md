## Definition
?
*A subset $\{v_{1},\dots,v_{k}\}$ is linearly dependent if there are scalars $a_{1},\dots,a_{k}$ not all zero, such that $a_{1}v_{1}+\dots+a_{k}v_{k}=\vec{0}$, else it's linearly independent*
<!--SR:!2025-06-28,15,292-->

## Examples
?
- $\{\vec{0}\}$ is linearly dependent since any scalar times $\vec{0}$ equates to $\vec{0}$
‎ .
- $\{u\}$ where $u\neq \vec{0}$, is linearly independent since only way to get the linear combination to equate to $\vec{0}$ is by multiplying u by 0
.
- $\{u_{1},u_{2}\}$ is linearly dependent iff one is a scalar multiple of another.
	Suppose $\{u_{1},u_{2}\}$ is linearly dependent. Then, assuming $a_{1} \neq 0$
	$$\begin{array}{l}
a_{1}u_{1}+a_{2}u_{2} = \vec{0} \\
u_{1}+\frac{a_{2}}{a_{1}}u_{2}=\vec{0} \\
u_{1} = -\frac{a_{2}}{a_{1}}u_{2} \end{array}$$
- $\{\sin x,\cos x\}\subset \mathcal{F}(R)$
	$\sin x=a\cos x$ for $a\neq 0$
	At $x = 0, 0 = a$, however since $a\neq 0$, the functions aren't same and thus the subset is linearly independent
<!--SR:!2025-06-25,12,272-->

## Worked-Out Examples
?
Determine if $\{u_{1},u_{2},u_{3}\} = \{(-1, 1, 2), (1, 2, 1), (5,1,-4)\}$ is linearly dependent or not.
	$a_{1}(-1,1,2)+a_{2}(1,2,1)+a_{3}(5,1,-4)=(0,0,0)$
$$
\begin{align}
-a_{1}+a_{2}+5a_{3}=0 \\
a_{1}+2a_{2}+a_{3}=0 \\
2a_{1}+a_{2}-4a_{3}=0
\end{align}
$$
Converting into Augmented Matrix & REF we get:
$$\begin{pmatrix}
	-1 & 1 & 5 & 0 \\
	1 & 2 & 1 & 0 \\
	2 & 1 & -4 & 0
	\end{pmatrix}
	\to
	\begin{pmatrix}
	-1 & 1 & 5 & 0 \\
	0 & 3 & 6 & 0 \\
	0 & 3 & 6 & 0
	\end{pmatrix}
	\to
	\begin{pmatrix}
	-1 & 1 & 5 & 0 \\
	0 & 3 & 6 & 0 \\
	0 & 0 & 0 & 0
	\end{pmatrix}
$$
Since the Augmented Matrix is in REF and has a column without a leading entry, this is linearly dependent set. If k=0, then there is only one solution to the system which is for all coefficients to be zero.
<!--SR:!2025-06-23,10,274-->

## Theorems
- [[Linearly Dependent Subset Vector as Linear Combination of Others]]
- [[Refinement Theorem]]
- Theorem 1.6, $S_{1} \subset S_{2} \subset V$, if S1 is linearly dependent, then S2 is linearly dependent.
- If S2 is linearly independent, then S1 is linearly independent

let S1 be linearly dependent, then there exist vectors s1, ..., sn and scalars a1, ..., an not all zero s.t a1s1 + ... +ansn = 0, 

Since S1 is a subset of S2, then all vectors of S1 are in S2, let S2 = {s1, ..., sn, sn+1, ... sk}

Then a linear combination of its vectors equating to zero is as follows:

a1s1+...+ansn+b1sn+1 + ... + bksk = 0

We need to show that S2 linearly dependent, assume not.

Then b1 = ... = bk = 0, but if so, the rest a1s1 + ... + ansn must have coefficients not all equal to zero per linear dependence of vectors in S1, thus S2 is linearly dependent.

Corollary:

If S2 is linearly independent, then for s1, ..., sk in S2 and a1, ..., an, b1, ... , bk

a1s1 + ... + bksk = 0 and all coefficients are 0.



#linear-algebra