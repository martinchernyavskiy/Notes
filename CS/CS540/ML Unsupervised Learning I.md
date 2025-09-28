
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
<!--SR:!2025-10-02,4,270-->

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
- Given data points, assume each starts within each own cluster
	- Merge 2 points (clusters) that are closest to each other
<!--SR:!2025-10-02,4,270-->

## Merging Criteria of Agglomerative Clustering
?
- How do we define whether clusters are closest?
	- Single-linkage
		- Given 2 clusters, use the point that has a minimum distance to that other cluster
	- Complete-linkage
		- Opposite of single-linkage
		- Minimizes the noise by including the outliers
	- Average-linkage
		- Get distance between each point from two clusters
<!--SR:!2025-10-02,4,270--> 

## Center-based clustering
?
- K-means is an example of center-based clustering algorithm
	- Must specify the k (amount of clusters)
- Logic (for k = 2)
	- Pick two random points as initial cluster centers (don't have to be data points)
	- For each point x determine its cluster based on closest center in Euclidean space
	- Get the mean of points within each cluster and make these as centroids of their respective cluster
	- Repeat until the centroids no longer move

## K-means algorithm
?
- Input is x data points and a k that specify the number of clusters
	- Step 1: Select k cluster centers (random points)
	- Step 2: For each x data point, assign it to the closest center in Euclidean distance
		- Have a function that finds the minimum distance between each point and each cluster center
	- Step 3: Update all cluster centers as the centroids:
		- Meaning get the mean of points within their cluster and assign it to be the new centroid
	- Repeat steps 2 and 3 until cluster centers no longer change
<!--SR:!2025-10-02,4,270-->

## K-means optimization problem
?
- The goal is to minimize the sum of distances from the points to the corresponding cluster center

## Does k-means algorithm stop?
?
- Yes, for fixed dataset and fixed number of clusters there are only finite number of ways to assign data points to clusters.
	- Each iteration assigns each data point to the closest centroid and then recomputes centroids as the mean of assigned points
	- So each iteration reduces the objective function
<!--SR:!2025-10-02,4,270-->

## Global vs. Local Optimum
?
- Finding global optimum using k-means algorithm isn't guaranteed, but we may find local
<!--SR:!2025-10-02,4,270-->

## How many clusters to use for k-means?
?
- Need domain knowledge and generally difficult to estimate
- Elbow Method
	- Get the within-cluster sum of squares for different values of k
	- Plot this vs. k and look for elbow point which is basically where reduction in WCSS slows down
<!--SR:!2025-10-02,4,270-->