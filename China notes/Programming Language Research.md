- Yingfei Xiong


### Programming Languages
- Why are there so many different type of languages? 
	Because it makes programming easier
	- Machine Code
	- Assembly Language
	- High-level programming languages (Imperative programming languages)

### Functional Programming Languages
- Functional and logical programming languages are a separate family
- Use functions to describe goal $\to$ computer finds the right computation
- Program: input $\to$ output
- Functional programming language takes the mathematics form of functions
- f(a, b) = a+b is supporte, but f(a+1, b+1) = a+b-2 has a limited support though pattern matching
- Families:
  - Lisp family (standard lisp, scheme, racket)
  - ML family (ML, Ocaml, F#)
  - Haskell

### Example of Functional Programming
```Haskell
quicksort[] = []
	quicksort(p:xs) = (quicksort lesser) ++ [p] ++ (quicksort greater)
	where
		lesser = filter (< p) xs
		greater = filter (>= p) xs

``` 

```Haskell
main = do
	let file = "abc.txt"
	contnets <- readFile file
	putStrLn contents
```


### Modern Features of Functional Programming
- High-Order Functions:
	- (MapReduce divides bigger task into smaller task, two standard functions in standard function map (+1) [1,2,3]] = [2.3.4]
	- reduce (+) [1,2,3] = 1+2+3 = 6)
- Algebraic data Types
- Structural Type System
- Functional Data Structures:
	- arr1 = [1,2,3,4, ...]
	- arr2 = change3rd(arr1)
	- Implementing functional arrays allows for an almost O(1) operation of changing an element in the array which is equipped with searching the element.
	- Backtracking (changing to initial state) is also reduced from O(n) to O(1)

- Modern programming languages are all functional
	- Java, C++, etc have labmda expressions
- New programming languages are functional
	- Scala, Kotlin, Swift, Rust

### Logic Programming Languages
- Describe with formal logic
- Let computer solve a problem described in logic 


### Example of Logic Programming

```Lua
grandmentor(X,Y) :- mentor(X,Z), mentor(Z,Y).
mentor(kongzi, mengzi).
mentor(mengzi, xunzi).
grandmentor(?X, xunzi)
```

- Very much similar to lambda expressions

### Large Scale Projects
- Maintenance and Reusability $\to$ Object-Oriented Programming
- Aspect-Oriented Programming
	- Dealing with cross-cutting concerns (want to write code only once and reuse it)
- Point cut: matching code
- Advice: modification to the code

### Domain-specific Languages (DSLs)
- Domain-specific tasks
- Database query language: SQL
- XML query language: XQuery
- Differentiable programming languages:
  - TensorFlow/Pytorch

### Probabilistic Programming Languages
- For building probabilistic models
- Standard R-code like

### Meta Programming
- Makes DSLs programming easier
- SAT solver is an algorithm that finds whether a logical statement is true

### Program Synthesis
- Specification $\to$ Program
- Compared to LLMs: ensuring correctness