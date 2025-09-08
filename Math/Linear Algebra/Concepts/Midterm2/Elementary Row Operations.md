
## Definition
?
*Performing an elementary row operation on a matrix can be described using matrix multiplication by an elementary matrix*

## Elementary Matrix
?
*An elementary matrix E of the three types of elementary row operations is obtained from In by applying the elementary row operations on it*
- E1 = (1 0 0 1) --> (0 1 1 0)
- E2 = (1 0 0 /\\)
- E3 = (1 0 /\\ 1)

## Rank of Matrix
?
*Rank of matrix A is the rank of its left-multiplication transformation*

## Theorems
- [[Elementary Matrix is Invertible]]
- There exists a finite set of elementary matrices such that multiplying them all by A results in A reducing to RREF (left most E.M is the last operation)
- Matrix A is invertible if there is a finite set of elementary matrices such that multiplying them by A results in an identity matrix (A | In)
		Inverse of A is then equal to the product of all of these elementary matrices
		A however is equal to the product of inverses of the elementary matrices in the opposite order
- From this it follows that A is invertible iff it can be written as a product of elementary matrices
- [[Rank of product of invertible matrix with a general matrix is equal to rank of the general matrix]]
	- Elementary row operations don't change rank
	- rank(A) = rank(RREF(A))
	- Given an RREF of A, its rank is the number of non-zero columns 
	- nullity of A is then the # of columns without leading entries by dimension theorem.




#linear-algebra

The ordered basis β for V consists of the actual eigenvectors, which are 2x2 matrices.

$$\beta = \left\{ \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}, \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}, \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}, \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix} \right\}$$The matrix representation $[T]_\beta$ is a **4x4 diagonal matrix** with the eigenvalues on the diagonal, corresponding to the order of the eigenvectors in $\beta$.$$[T]_\beta = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}$$