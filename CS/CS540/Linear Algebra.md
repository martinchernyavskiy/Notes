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
		- Av = cv where v is nonzero eigenvector and c is eigenvalue
		- A is a linear transformation such that it stretches / rotates vectors

## Dimensionality Reduction
?
- Vectors can store a lot of features
- We are willing to reduce dimensions since a lot of features are redundant and it takes a lot of storage and computation resources
- Thus, we attempt to reduce the dimension to minimize information loss

## Principal Components Analysis (PCA)
?
- A type of dimensionality reduction approach, data is approximately lower dimensional
- Allows to find axes (vectors) of a subspace which will project to this subspace
- We want to preserve data, minimize projection error
- Vectors like this are called *principal components*
- In a 2d example, the goal is to find a line that minimizes the sum of squared distances to xi's
	- the *optimal* line is called principal component 1 
- Given arbitrary input of vectors
	- We center data so that the mean of these vectors is equal to 0
- We obtain as an output the principal components which are orthogonal 
	- We also obtain covariance matrix (dxd) which describes how the different dimensions of the data vary together $S=\frac{1}{n-1}\sum_{i=1}^{n}x_{i}x_{i}^T$ 
	- Principal components are the top-m eigenvectors of this covariance matrix

## Dimensionality Reduction Variations
?
- PCA, Kernel PCA, ICA, CCA
- Used for visualization, efficiency, noise removal, downstream machine learning use, etc.
- *Application*
	- Image compression
		- Divide image to 12x12 patches, we have 144-d vector
		- We obtain 6 principal components as an image and thus able to project the image to 6D