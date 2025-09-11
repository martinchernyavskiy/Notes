## Usage
?
- Linear Functions are simple and tractable
	- Building blocks for all models (linear regression, part of neural networks)
- Vectors
	- Can be list of values or point in space
	- Dimension
	- In AI/ML we use particularly high dimensions
- Matrices
	- Table of values / vectors
	- Represent linear transformations
	- If we apply to a vector, we get another
	- mxn dimension
	- Can easily index into matrix
- Transposition
	- Flips rows and columns

## Matrix & Vector Operations
?
- Vectors
	- Addition
	- Scalar Multiplication (uniform stretch / scaling)
	- Inner product (dot product)
		- $<x,y> := x^Ty=[x_{1} x_{2} x_{3}] \begin{pmatrix} y_{1} \\ y_{2} \\ y_{3}\end{pmatrix}$ = x1y1 + x2y2 +x3y3
	- Outer product
		- $xy^T=\begin{pmatrix}x_{1} \\ x_{2} \\ x_{3}\end{pmatrix} \begin{pmatrix}y_{1}  & y_{2}  & y_{3}\end{pmatrix} = \begin{pmatrix}x_{1}y_{1}  & x_{1}y_{2} & x_{1}y_{3} \\ x_{2}y_{1} & x_{2}y_{2} & x_{2}y_{3} \\ x_{3}y_{1} & x_{3}y_{2} & x_{3}y_{3} \end{pmatrix}$ 
	- 