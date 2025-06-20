### Decimal
- Put plus / minus in front of a number to indicate its sign (usually omit plus sign). We call it a signed-magnitude

### Binary
- The most-significant bit is the sign (1 is negative)
- Remaining bits are number's magnitude (0010 for +2, 1010 for -2)
- Easy for humans, hard for computers since it affects arithmetic


### 2-s Complement Representation
- Ignore any carry from the most-significant bit position
- For N-bit number, the sum looks like 2^N
- Positive numbers always start with 0 an use normal positional notation
- Negative numbers always start with 1.
	For humans it's easiest to use negative to determine binary sequence for a negative number
	To negate: $-X = 2^N - X$, since actual sum  