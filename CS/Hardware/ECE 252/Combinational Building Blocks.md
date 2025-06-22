### Decoders
- Converts an n-bit input codeword into a unique m-bit output value, where $m = 2^n$
- There are $2^n$ unique n-bit inputs for each of which there is only one unique m-bit output value
- Input signal values determine which output can be true
- An analogy would be the telephone system where the input is the phone number of a person and the output is the phone ringing (decoder output is true), while for the rest people in the world the phone doesn't ring
- Example of decoders:
	1-2 decoder
	2-4 decoder
	3-8 decoder
- Outputs are labeled with the value of the input code
- Inputs are labeled based on how they should be arranged to form a binary number
- Input value matches the output value
- Input label numbers depict the position of the n-bit
- Labeling inside the symbol is based on the fundamental operation of that structure, whereas signal names (values) outside of the symbol are based on how we choose to use the structure in a digital circuit


### Multiplexers
- Combinational logic circuit that performs a selection
- Selects input which is used to drive the output.
- There are a total of n select lines and 2^n data input lines, but one output
- Named by input-output(1) ration.
- Select input selects the data input channel which drives the output. Data input is a particular signal 
- Analogy is a selection of tv channel

- There is a decoder inside the multiplexer, helping to decode the select input


### Adders
- Combinational circuit that produces the sum of two binary numbers
- A full adder takes 3 inputs, 2 bits from the addends and 1 for carry value from bit position to the right. Outputs a sum bit and a carry value to send to the next position to the left
- A half-adder is a combinational circuit that accepts two addend bits but no carry value
- Adding a pair of multi-bit addends requires to connect as many full adders together as there are bit positions in both addends
- CoutS = A + B + Cin