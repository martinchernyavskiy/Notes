## Graph-based / Proximity-based clustering
?
- G = (V,E), V = set of vertices, E = set of edges
- Edges can be weighted or unweighted
- *similarity*: based on weights, one that have high weight edges between them are more similar than ones with low weight edges or none at all
- Want: partition V into two different set of vertices
	- Cut by the edge with smallest weight to separate V into two sets
	- Partitioning V into larger number of clusters is the sum of # of cut edges from a cluster from others divided by 2 to account for overcounting the edges

## Partition-Based Clustering
?
- Use *spectral matrix approach* that utilizes *adjacency matrix* (one that has entries of 0 and 1 based on whether the 2 vertices share an edge between each other) and *degree matrix* (entries of number of edges each vertex has)
- Obtain *Laplacian Matrix*: L = D - A, encodes the graph and the strength of each node
	- Compute k smallest eigenvectors of L
	- Create U matrix of nxk dimension with each of mentioned eigenvector as column vectors of this matrix
	- Run k-means to get the final clustering

## Why normalized Laplacian?
?
- Minimizing the weight of the cut may result in one of the nodes to be cut off completely. So we need a *balanced* cut
	- Use volume, which is the sum of the degrees of each vertex in cluster
	- Dividing the partitioning formula by it would then normalize it

## Spectral Clustering
?
- Uses Laplacian Matrix while PCA used covariance matrix.
- Use smallest eigenvectors because they give partitioning information.
- Why use it?
	- No need for points or distances as input
	- Can handle intuitive separation

## Visualization (T-SNE)
?
- PCA can be used for visualization but it's not specifically designed for it
	- Thus the visualization may not be meaningful for us
- Instead an example of a visualization algorithm is *T-SNE*
	- Allows to project data into 2 dimensional space that provides a better visualization for cluster of images

## T-SNE Algorithm Steps
?
- We first turn probability vectors into probability pairs and then turn those pairs back into lower-dimensional vectors (the closer the points are, the higher their probability is and vice versa)
- Step 1: Gaussian distribution
- ![[Pasted image 20251003172705.png]]
- Step 2: Student t distribution
- ![[Pasted image 20251003173157.png]]

## Density Estimation
?
- Given samples from some distribution, we want to estimate the distribution
- We may use a histogram, given the samples, we label them on the graph and define the bins and count the number of samples in each bin. Then we normalize
	- The problem is that for high dimensions most of the bins are empty
	- Not continuous
	- Ambiguity in choosing the bins
- Instead use *Kernel Density Estimation*
- ![[Pasted image 20251003174107.png]]
	- Where K is the Kernel function (gaussian), h is the width parameter