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