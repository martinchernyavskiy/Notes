
## Definition
?
*A linear operator (linear transformation from and to the same vector space) is diagonizable if there exists a basis of V for which the matrix representation of T is diagonal matrix (if there is a basis of eigenvectors)*

## Eigenvectors and Eigenvalues
?
- Eigenvector of a linear operator is non-zero v in V for which T(v) = cv ; v is scaled
- The scalar c is the eigenvalue if there exists v in V for which T(v) = cv
- Thus, T is diagonalizable iff there exists a basis consisting of eigenvectors, which result in matrix representation of T to be a diagonal matrix with eigenvalue entries

## Examples
?
- Find eigenvectors of A ( 0 0 1 
					 0 2 0
					 -2 0 3) with eigenvalue 1
- That means we need all nonzero vectors in N(A - I3), solve for the matrix and read off the solution set from RREF.
- Given A( 0 -1 1 0) and f(t) = det(A - tI2), det of the latter matrix is t^2 +1 which has no real roots and thus A has no eigenvalues.


## Eigenspace
?
*Given an eigenvalue of A, eigenspace of A corresponding to that eigenvalue is Ec = N(A - cIn), set of all eigenvectors for eigenvalue or 0*

## Characteristic polynomial
?
f(t) = det(A - tin) is the characteristic polynomial of A where it is a polynomial of degree n. Solving for the determinant gives eigenvalues of A 

## Algorithm for Diagonalization
- Find eigenvalues of A using characteristic polynomial
- Using eigenspace, find basis for each eigenvalue
- Attempt to combine the bases to form a basis for V, if sum of dimensions = n, then we found the basis
- Compute change of coordinates

## Algebraic and Geometric Multiplicity
- Given an eigenvalue c of A,
- Algebraic multiplicity of c: number of times (c -t) divides det(A - tIn)
- Geometric multiplicity of c: dimension of eigenspace of c

## Theorems
- Matrix is diagonalizable if its left multiplication transformation is.
	- If there exists Q for which Q^-1 A Q is diagonal
- v in Rn is eigenvector of A if its in kernel of N(A - cIn)
- A scalar is an eigenvalue of a matrix iff det(A - cIn) = 0
	- If c is an eigenvalue, then there exists a non-zero v in V for which Av = cv
	- --> (A-cIn)(v) = 0 for v != 0
	- --> kernel of this is not equal to zero
	- --> A-cIn i snot 1-1 and thus not invertible and thus its determinant is 0
- c is eigenvalue of A iff c is a root of the characteristic polynomial & A has at most n eigenvalues
.
- Eigenvectors of distinct eigenvalues are linearly independent 
.
- If A is diagonalizable, then its characteristic polynomial splits over R
	- Let A be diagonalizable, then there is a basis for which its left multiplication matrix representation is diagonal.
.
- If A and B are similar, then they have the same eigenvalues
	- det(B - tIn) = det(Q^-1AQ - Q^-1 tIn Q)
	- = det(Q^-1)det(A-tIn)det(Q)
	- = det(A-tIn)
.
- Geometric multiplicity is less than or equal to algebraic multiplicity
.
- A is diagonalizable if its characteristic polynomial splits over R and for each eigenvalue, geom mult = alg mult




#linear-algebra