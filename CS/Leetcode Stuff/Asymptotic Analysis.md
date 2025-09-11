## Analyzing Algorithms
?
- Time complexity (runtime)
- Space complexity (memory)
- I/O (disk reads/writes)

## Basic Operations
?
- Based on *RAM model*
- Arithmetic (add, subtract, multiply, divide)
- Data movement (load, store, copy)
- Control (branching, subroutine calls/returns)
- shift left - 2^k allows to compute in constant time

## Ram Model
?
- Data types are integers and floating points
- Word size can't grow arbitrarily large
- *Word* is a unit of data with a defined bit length that can be handled by the instruction set and moved between storage and the processor
- Ignore memory hierarchy (caches)

## Runtime
?
- Number of primitive steps or operations we execute 
- Each line of pseudocode executes in constant time
- ith executes in ci where c is constant
- subroutines - calling is constant time, but executing may not be constant time
- generally grows with the size of input 
	- For sorting, number of items in array
	- For graphs, number of vertices or edges