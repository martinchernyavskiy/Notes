## Ways of base conversion

- ### Repeated division by base (General)
	- Repeatedly divide by the base number, substituting remainder in the digit's place until left with 0 quotient
	Example:
	To convert from decimal to hexadecimal:
		Divide by 16 and place remainder in the one's place
		Next divide the quotient (number after division) by 16 again and place remainder as the next digit
		Repeat the process until a 0 quotient

- ### Decimal to Binary
	Find smallest binary number value that is less than or equal the decimal value and subtract it from the value. 
	If binary number value is greater, put a zero digit on that digit's place and continue

- ### Binary to Hex
	Directly substitute hex digit for a 4-bit binary number or vice versa
	This works because: $16 = 2^4$, one base16 digit can represent all possible combinations of 4 base2 digits

- ### Binary to Octal
	Same as to Hex, but substitute octal digit for a 3-bit binary number and vice versa


- ### Converting between 