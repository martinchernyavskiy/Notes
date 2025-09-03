- Describe solution in terms of solutions to easier instance of the same problem
- Definitions, algorithms, programs
- *recursive call* is a function call by a function to itself, using smaller input
- it is essential for input to become smaller to eventually reach the base case for which solution is is easily obtained and that unravels all of the recursive calls from last to first


## Fibonacci
- Recursive definition = $F_{n} = F_{n-1} + F_{n-2}$
- Foundation rules F1 = 1 and F2 = 1 are base cases
This can be turned into a recursive program that calculates the n-th fibonacci number:
Input: n - a positive integer
Output: Fn - the n-th Fibonacci number
```
Fib(n)
if n = 1 or n = 2 then return 1
	else return Fib(n-1) + Fib(n-2)
```

## GCD
Input: a,b - positive integers
Output: gcd(a,b) - their greatest common divisor
```
GCD(a,b)

if a = b then return a

if a < b then return GCD(a, b-a)

if a > b then return GCD(a-b, b)

```

## Correctness of Recursive Programs
- When prove correctness, we prove that for all valid inputs, the program produces the correct output
- Need to prove correctness via induction. Proving correctness involves proving partial correctness and termination
### Partial Correctness
- Need to show for all valid inputs x, if program terminates, then it returns the correct output for x
- For recursive programs it is sufficient to show:
	- All recursive calls on input x are valid inputs
	- Assume these recursive calls return the correct output and that the program terminates, the program returns correct output on x
- The structure of partial correctness proof mimics the structure of recursive program under consideration.
	- First prove that program returns correct output on simplest inputs (similar to base case in induction)
	- Then prove that inputs to recursive calls are valid and if recursive calls return the correct output, then the program returns correct output (similar to inductive step in induction)
	- If program terminates on input, then the chain of recursive calls it makes will end at the simplest input, which is implied by partial correctness that program returns the correct output
### Termination
- Proved by induction on some quantity (depends on the inputs) which decreases with each recursive call