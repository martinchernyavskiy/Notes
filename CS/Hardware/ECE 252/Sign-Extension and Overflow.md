### Sign-Extension
- Value can be represented using different number of bits.
- In unsigned binary, we can append 0s to the left of a number to make the bit-widths match the adder. This is called *zero-extension*
- For 2-s Complement Representation, for positive numbers zero-extension works as expected, however for negative ones it doesn't.
- For signed numbers, we replicate the sign bit as many times needed, in the process called *sign-extension, inserting 0s for positive numbers, 1s for negative numbers*
- Logic for using fewer bits works the same, but make sure the sign bit remains intact 

### Overflow
- Answer to computation is not representable in the number of digits the answer has.
- "Is the answer correct?" - Yes/No
- In signed binary overflow, carry-out doesn't mean there has been an overflow
	If numbers have opposite signs, overflow cannot occur since the result must be in the interval between them
	If numbers have the same sign, but the sign is different, then the result overflowed