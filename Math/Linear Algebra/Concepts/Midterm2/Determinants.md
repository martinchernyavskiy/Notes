
## Definition
?
*Determinant is a map from vector space of square matrices to R*

## Properties / Axioms
?
1. A is invertible iff det(A) != 0
2. det(A) has a geometric meaning
		Let (0,1)^n be a binary string
		This defines a cube that is determined by {e1, ... , en}
		Given a square matrix A, left-multiplication transformation on this binary string defines a parallelepiped  that is determined by {Ae1, ... , Aen}
		Then volume of this left-multiplication transformation is the absolute value of det(A)
3. det is not linear except for n=1
4. det(AB) = det(A)det(B)

## Inductive Definition of Determinant
?
Det is a map that is inductive on n (# of rows / columns in a square matrix).
For n=1, M_1x1 and det(a) = a
	Inverse of a is 1/a iff a = det(a) != 0
	Left-multiplication defined on this 1x1 matrix is a map from R to R.
		This transformation applied on a binary string equates to (0,a) if a>= 0 and (a,0) if a <0
		Vol of this transformation = |a| = |det(a)|
	det is linear for n=1
	det((a)(b)) = det(ab) = ab = det(a)det(b)
For n=2, M_2x2 and det(A) = ad-bc
	2x2 matrix is invertible if 

## Non-examples
?
- Non-example 1: ...
- Non-example 2: ...

## Theorems
- [[Theorem Name 1]]
- [[Theorem Name 2]]




#linear-algebra