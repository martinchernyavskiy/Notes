
## Definition
?
*An inverse of T : V --> W is S : W --> V such that T(S) = Iw and S(T) = Iv. If T has an inverse, it is said to be invertible. Inverse of T is unique and denoted by $T^-1$*

## Properties / Axioms
?
1. $(TU)^-1=U^-1T^-1$
2. $(T^-1)^-1= T$, inverse of T is invertible
3. *Function is invertible iff it is both 1-1 and onto*. That is, T is invertible iff rank(T) = dim(V) by theorem 2.5 where V and W are of equal dimension
<!--SR:!2025-08-30,3,250-->

## Examples
?
- T: P1(R) to R^2 is linear defined by T(a+bx) = (a, a+b). Then its inverse is T^-1 : R^2 to P1(R) defined by T^-1 (c,d) = c + (d-c)x
- If $L_{A}$ has an inverse, it is $L_{A^-1}: \mathbb{R}^n \to \mathbb{R}^n$. It's only possible if n = m since a linear map has an inverse iff it's 1-1 and onto --> dimR^n = dimR^m 

## Matrix Invertibility
?
- Let A be an nxn matrix, then it is invertible if there exists an nxn matrix B such that AB = BA = I. Such matrix B is unique and denoted by A^-1
.
- To find inverse of a generic 2x2 matrix we need to create an augmented matrix (A | In) and reduce it to RREF. Once that is done, we get (RREF (A) | B) and if RREF (A) is In, then B is inverse of A.
<!--SR:!2025-08-28,1,230-->


## Isomorphism
?
- Two vector spaces are isomorphic if there exists an invertible linear map between them, such linear map is called *isomorphism*. This is only the case when the two vector spaces are of same dimension,


## Theorems
- [[Inverse of a Linear Map is Linear]]
- For linear and invertible map, if beta is basis of V, then T(beta) is basis of W. From this it follows that dimV=dimW if map is invertible
- [[For a invertible linear map, V is finite dimensional iff W is finite dimensional]]
- [[T is invertible iff its matrix representation is invertible]]
- [[Matrix is invertible if its determinant is non-zero]]

## Questions
- ...
- ...
- ...



#linear-algebra