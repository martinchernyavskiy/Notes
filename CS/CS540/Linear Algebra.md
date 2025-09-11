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
- *Vectors*
	- Addition
	- Scalar Multiplication (uniform stretch / scaling)
	- Inner product (dot product)
		- $<x,y> := x^Ty=[x_{1} x_{2} x_{3}] \begin{pmatrix} y_{1} \\ y_{2} \\ y_{3}\end{pmatrix}$ = x1y1 + x2y2 +x3y3
		- If equal to 0, then x and y are orthogonal
	- Outer product
		- $xy^T=\begin{pmatrix}x_{1} \\ x_{2} \\ x_{3}\end{pmatrix} \begin{pmatrix}y_{1}  & y_{2}  & y_{3}\end{pmatrix} = \begin{pmatrix}x_{1}y_{1}  & x_{1}y_{2} & x_{1}y_{3} \\ x_{2}y_{1} & x_{2}y_{2} & x_{2}y_{3} \\ x_{3}y_{1} & x_{3}y_{2} & x_{3}y_{3} \end{pmatrix}$ 
	- Vector norms: "length"
		- $||x||_{2}=\sqrt{ \sum_{i=1}^{n}x^2_{i} }$
	- Set of vectors is orthonormal if for every pair of vectors their dot product is 0 and for all x_i, the length is equal to 1
- *Matrices*
	- Addition
	- Scalar Multiplication (Stretching the linear transformation)
	- Matrix-vector multiplication (left multiplication transformation)
		- Feedforward Neural Networks with input x:
			- $f^k(x)=\sigma(W^T_{k}f^{k-1}(x))$
			- Where sigma is nonlinearity, W is weighted matrix for layer k (linear transformation), output of layer k-1 is a vector and we produce an output of layer k which is also a vector
	- Matrix Multiplication (composition of linear transformation)
	- Identity Matrix
		- rows and columns consist of standard basis vectors
	- Matrix Inverse
		- A matrix is invertible if there is B such that AB = BA = I
	- Eigenvalues and EIgenvectors
		- Av = cv w