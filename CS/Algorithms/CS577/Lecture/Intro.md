## Algorithm/Program Specification
?
- *Importance:*
- What are effects but not how they are achieved
- Modular design, can easily understand what the algorithm/program does without delving into details
- Correctness
- *Components*:
	- Valid inputs
	- Correct output
	- Side effects (if any on data structures)
- *Properties*:
	- Unambiguous
	- Succint 
	- Stand alone
- *Example*:
	- Greatest Common Divisor
		- Input: a,b in $\mathbb{Z}_{>0}$ 
		- Output: gcd(a, b)

## Algorithm Correctness
?
- *Proof that algorithm realizes the specification. Meaning for all valid inputs the algorithm products correct output*
- Split into two parts:
	- Soundness (Partial Correctness)
		- Algorithm is correct on every valid input on which it terminates
	- Termination
		- Algorithm terminates on every valid input
- Oftentimes we combine these two 
- Conducting a runtime analysis eliminates need for termination argument

## Correctness Example for Recursive Algorithm
?
-  Input: a,b in $\mathbb{Z}_{>0}$ 
-  Output: gcd(a, b)
	- procedure GCD1(a,b)
		- if a = b then return a
		- if a < b then return GCD1(a, b-a)
			- else return GCD1(a-b, b)
- Soundness is proved by induction on recursion depth
- Termination is proved by induction on complexity measure a + b
- Combined: By induction on some complexity measure a + b

## Correctness of Iterative Algorithm
?
-  Input: a,b in $\mathbb{Z}_{>0}$ 
-  Output: gcd(a, b)
	- procedure GCD0(a,b)
		- x <- a; y <- b
		- while x != y do
			- if x < y then y <- y-x
				- else x <- x-y
		- return x
- Soundness is proved by loop invariants
	- These are statements that hold each time the loop condition is checked
	- Example: gcd(x, y) = gcd(a, b)
	- Loop invariants and negation of loop condition imply correct output
- Termination: No infinite loop

## Abstract Data Types
?
- Min Priority Queue (binary heap)
	- Contains elements with certain keys that denote priority
	- For insertion the complexity is O(log(n))
	- For finding minimum O(1), minimum is the top most element
	- For extracting minimum O(log(n))
	- For decreasing key O(log(n))
	- For initial creation O(n)
- Dynamic Dictionaries (use balanced binary search trees)
	- Objects have keys
	- Find/Insertion/Deletion is O(log(n))

## Diagraph Representations
?
- G = (V,E)
	- Typically use n to determined number of vertices and m for number of edges
- To use graph as input/output we need a way to encode it
	- *Adjacency matrix*: 
		- Matrix in which rows and columns correspond to each vertex and the entries denote whether the intersection row/column vertices have an edge pointing to the other.
		- Efficient for looking up entries in constant time. Traversing path is inefficient however (where edges have direction)
		- Consumes n^2 bits
	- *Adjacency Lists*
		- Lists out every vertex in order on separate line and denotes after colon which edges that vertex points to
		- n+m words of O(log(n)) bits
	- Linear time: O(n+m) time assuming adjacency lists

### Graph Traversal
?
- Visit all vertices and edges reachable from a given vertex v my moving along edges from already-visited vertices
- Common algorithms DFS and BFS
- For undirected graphs, edges leading to new vertices form a *spanning tree* of connected component of v
#### Strategies
- Stack for DFS, Queue for BFS
	- BFS: start with given vertex, add it to queue
		- Add all of its non-visited neighbors to the queue
		- Remove the front of the queue and repeat
	- DFS: start with given vertex, push it on stack
		- Add one of its neighbors to the stack that was not yet visited
		- Now that this neighbor is on top of the stack, continue same process until either we have reached all vertices or in the case of a dead-end, pop from stack until find a not-yet visited neighbor
	- These two assume we keep track of visited vertices
- BFS is iterative and DFS is recursive
- Non-tree edges
	- For BFS their level difference is <= 1
	- For DFS their level difference based on ancestor-descendant relation
- Both run in linear time assuming Adjacency List

### Topological Sort
?
- Specific to directed acyclic graphs
- *Ordering of vertices on a line such that edge only go in one directions*
- Want to start with a vertex with no incoming edges
	- This is possible only if a graph is acyclic
	- After removing a vertex from acyclic graph, the graph remains acyclic and we repeat the process until none exist
- In order for above algorithm to work we need to keep track of all vertices and their in-degrees
	- Use adjacency list to decrement the in-degrees of edges related to a popped vertex