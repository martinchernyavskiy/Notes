
### Intro

- Prioritiy Quee 
	- Maintain a set of elements S and each has an associated value k.
	- insert / minimum / extract min / decrease x by k / create 
	- implemented via heap. value of parent <= child value
- Dynamic Dictionary
	- Find: O(log(n))
	- Insertion / deletion (O(log(n)))

- Graphs
	- *Must mention implementation*
		- Adjacency Matrix:
			- Imagine nodes are labelled 1 through n
			- A(i,j) is 1 iff there is edge between i to j vertices
	- If graph is not sparse, it's not so great O(n^2) edges

- Adjacency List
	- for every node, we maintain a list it's connected to
	- good for sparse graphs

- BFS and DFS
- Topological Sort
	- Directed acyclic graph, return nodes in some order subjected to a certain condition if node i is before node j, there is no connection of j to i
### Warm-up problems


#### 1.  Have two integers a,b where b >= 1
- Want a^b in O(log(b)) multiplications
- Multiplication is one unit of cost

- Algorithm candidate:
	- We need log of (b) steps
	- Can recursively split b since (a^2)^2 = a^4 


#### 2. 

- d = depth
- 



### Regular Problems


#### 3.



#### 4.



#### 5.