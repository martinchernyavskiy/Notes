### Algorithm Correctness
?
- modular design
- valid inputs (mention constraints)
- correct output
- side effects
- stand alone
- soundness (partial correctness)
	- algorithm behaves correctly on every valid input on which it terminates
- termination
	- terminates on every valid input
.
- combine soundness and termination
- also will upper-bound runtime, which eliminates need to show termination
- for iterative
	- loop invariants: gcd(x, y) = gcd(a, b). Statements that hold each time the loop is checked
	- Loop invariants holding and the negation of loop condition implies correct output
	- proof termination by induction, no infinite loop


#### Abstract Data Types
?
- Min priority queues (binary heap)
- Dynamic Dictionary (balanced binary search trees)

#### Graph Basics
? 
- G = (V, E), n = V, m = E 
	- adjacency matrix (n^2 bits)
	- adjacency list (n+m words of O(log(n)) bits)
	- Linear time (O(n+m)) - adjacency list is default
- Graph Traversal
	- visit all vertices and edges reachable from a given vertex v
		- breadth/depth first search
- BFS: queue, iterative,  
- DFS: stack, recursive

### Divide & Conquer
?
- 

#### Merge Sort
?
- 

#### Sorting Lower Bound
?
* 

#### Counting Inversions
?
* 
