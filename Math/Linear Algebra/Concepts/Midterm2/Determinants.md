
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
	2x2 matrix is invertible if ad-bc != 0
	det(AB) = det(A)det(B) which we can get by multiplying A by B and simplifying its determinant
For n>=2 and A in M_nxn
	Define a (n-1)x(n-1) matrix obtained from A by deleting ith row and jth column and call it B (A with squiggly line above it)
	*Then, det(A) = $\sum_{j=1}^{n}(-1)^{1+j}A_{1j}\det(B_{1j})$*

## Det and Row Operations
- Let B be a matrix after given elementary row operations, then:
- For row swap, det(B) = -det(A)
- For row multiplication, det(B) = cdet(A)
- For row add of multiple of other, det(B) = detA

## Theorems
- [[det(A) is linear in rows of A]]
- [[Fixing any row results in the same determinant]]
	- If matrix has row of all zeroes, then detA = 0
	- If matrix has two identical rows, then detA = 0
- det of upper / lower triangular matrix is product of its diagonal entries adjusted for how row operations may have changed the determinant




#linear-algebra