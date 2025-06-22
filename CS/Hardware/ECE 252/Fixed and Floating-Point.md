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
- Can encode radix point location into the number