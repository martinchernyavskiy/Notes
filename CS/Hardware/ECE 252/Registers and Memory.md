### Registers
- A register is a group of flip-flops used to store multi-bit binary values
- All of flip-flops in a register are controlled by the same clock signal 
  Drawn at a higher level of abstraction
- Input and output pins that are not single bits are labeled with a slash and number of bits and drawn as a heavier line than the single bit wires and are called buses
- Ripple full adders can also be represented as a block and both of them can be used to represent larger bit counters

### Registers with Enable
- We might want a register to hold a value for longer than just one clock period
- Add a multiplexer to choose to store a new value or the value already in the flip-flop, since there is no way to stop clocking the flip-flops reliably
- Selection signal in this multiplexer is called "enable"
	- EN = 0, keep current state
	- EN = 1, switch to next state
- Question for later, is every flip-flop equipped with a multiplexer then in a register?

### Memory concepts
- Memory has locations where data is stored
- Each location has a unique address
	- M-bit number that specifies which of the 2^M locations to access
	- Stores a single N-bit word (where N is number of bits referred as a data size of memory)
	- All bits are accessed simultaneously
- Capacity of memory is the total number of bits it can store (2^M * N)
- Only one location can be accessed at a time in scope of the class
- Write enable signal (WE) controls whether addressed locat