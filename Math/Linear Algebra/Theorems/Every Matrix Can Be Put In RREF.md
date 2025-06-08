### Theorem: Every matrix can be put in RREF by a finite sequence of elementary row operations
?
#### Proof: 
The elementary row operations in question are:
1. $R_{i} \leftrightarrow R_{j}$
2. $R_{i} \leftrightarrow cR_{i}, (c\neq 0)$
3. $R_{j} \leftrightarrow R_{i} + cR_{j}$
We will proof by construction (Gauss Elimination).
Consider matrix: $$\begin{pmatrix}
0 & 1 & 2 & 3 \\
1 & 1 & 1 & 1 \\
3 & 2 & 1 & 2
\end{pmatrix}
$$
A forward pass to REF:
i) Using (1), swap 1st and 2nd rows in order to put non-zero entry at the top of the leftmost non-zero column.
$$\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 1 & 2 & 3 \\
3 & 2 & 1 & 2
\end{pmatrix}
$$
ii) Then, use (3) to get 0s below this entry.
$$
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 1 & 2 & 3 \\
0 & -1 & -2 & -1
\end{pmatrix}
$$
iii) Ignore row with leftmost leading entry and repeat step (i) and (ii).
$$
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 1 & 2 & 3 \\
0 & 0 & 0 & 2
\end{pmatrix}
$$
The matrix is now in REF $\checkmark$
Now we need 
This completes the proof. $\square$

### Immediately follow:

#### 1.RREF of a matrix is unique
#### 2. Solution set of a linear system w/ augmented matrix in RREF is easily described in a standard way