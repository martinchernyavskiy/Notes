### Decimal
- Put plus / minus in front of a number to indicate its sign (usually omit plus sign). We call it a signed-magnitude

### Binary
- The most-significant bit is the sign (1 is negative)
- Remaining bits are number's magnitude (0010 for +2, 1010 for -2)
- Easy for humans, hard for computers since it affects arithmetic


### 2-s Complement Representation
- Can represent both positive and negative values
- Ignore any carry from the most-significant bit position
- For N-bit number, the sum looks like 2^N 
- Positive numbers always start with 0 an use normal positional notation
- Negative numbers always start with 1.
	For humans it's easiest to use negative to determine binary sequence for a negative number
	To negate: $-X = 2^N - X$, since number and its negative sum to 2^N, however there is an easier way.
	*Complement each bit and then add 1.
	So $0010_{2} \to 1101_{2} + 1_{2} = 1110$*
	*To know what negative number value we have, we first apply bitwise complement and add 1 to get a positive number representation which is the initial negative value, but positive.*

 - Unsigned binary represent non-negative values
 - In 2-s complement representation, half of the sequences represent same non-negative values, while the other half represents negative values, so we need to know the format.

### Addition of 2-s Complement Representation

- Works the same as for unsigned binary numbers, however carryout is omitted 

### Subtraction of 2-s Complement Representation

- Same as addition but add the negation of the value we wish to subtract from


### Operands bit-widths must match
- In order for math to work for 2-s complement arithmetic, operands and results must have the same number of bits which can be accomplished by [[Sign-Extension and Overflow]]