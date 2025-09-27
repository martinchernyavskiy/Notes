
## Supervised Learning
?
- Allows to make predictions, classify data, perform regression
- Has features and labels and the goal is to find a function with minimal loss to predict label on future data

## Unsupervised Learning
?
- No labels; not trying to make predictions rather finding a pattern/structure to understand the data
- Clustering / Hierarchical Clustering / Centroid-based Clustering
- PCA is also an unsupervised algorithm
- Estimating probability distributions is too

## Clustering
?
- Hierarchical Clustering
	- Agglomerative: start with every point being its own cluster and then merge
	- Divisive: start with all points being within a single cluster and then divide
- Partitional
	- Center-based: assign centers and determine which data points are closer to which centers (e.g k-means)
	- Graph-theoretic
	- Spectral
- Bayesian
	- Decision-based
	- Nonparametric

## Hierarchical Clustering
?
- Grouping points together based on whether they are similar to each other
	- Move from specific to general
	- no need for k

## Agglomerative Clustering
?
- G