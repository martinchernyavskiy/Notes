### Digital Circuits
- Manipulate voltage levels (abstractly 1s and 0s)
- Called logic circuits because they process and produce boolean results

### Logic Operators
- Logic functions are statements using logical operators for given operand values
- AND (dot or omitted)
- OR (plus)
- NOT (overbar)
- To convert truth table to function, OR together terms for all rows where result is 1

### Logical Equivalency
- Given two functions, they are logically equivalent iff their truth table match for each input combination

### Operator Precedence
- And > or > not
- Parentheses force order of evaluation
- Not alters everything which is below the bar. And turns into or, or turns into end. Implies parantheses
- XOR (exclusive or), (plus sign in circle)
- Intermediate columns 
- Odd function = XOR'ing more than two operands, since it's output going to be one only if odd number of its inputs are 1

### Bitwise Logic Functions
- Bitwise operation computes each bit of result based on the values in the corresponding position of the N'bit operand(s)