### Decimal 
- In decimal non-integer, each digit past radix point (decimal point in decimal) a base raised to the negative of the digit's position number, starting at 1 as first position after radix point


### Other Bases
- Real numbers for other bases follow the same logic as for the decimal. We can extend the idea of digit positions to include negative position numbers.
- Radix point separates integer portion from the fractional portion of the number
- N-digit non-negative number with radix r 


### Fixed-Point Binary
- Format defines a fixed position for radix point.
- We can also multiply the number to make it whole, calculate the value and divide by the same of what we multiplied by (base^n)
- Converting decimal to a fixed point binary number is the same, we just include negative exponents
- Need to determine in advance how many fractional bits we need

### Radix point isn't visible
- It's defined by a particular format, not encoded in the number itself. Thus, there is a need for instruction 


### Floating-Point
- Can encode radix point location into the number (not fixed in one place)
- Scientific notation is an example of a floating point where the exponent determines the position of the radix point. 
- Scientific notation is normalized, meaning there is exactly one non-zero digit left of the written radix point

### IEEE 32-Bit Floating-Point
- Float programming datatype refers to this format
- Most significant bit is signed bit (31)
- Signed-magnitude format
- Exponent field (30-23), remaining bits are used for significand
- Equation: $(-1)^{sign} \times 1.significand \times 2^{exponent-bias}$
- Bias equals to 127
- Standardizes format to facilitate exchange of data, however leading one for significand prevents from representing zero
- Special cases include:
	Zero, infinities, NaN values. For 0, s
- Bias helps to be used instead of 2-s complement so that comparison is easier