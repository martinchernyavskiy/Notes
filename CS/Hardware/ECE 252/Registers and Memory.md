### Registers
- A register is a group of flip-flops used to store multi-bit binary values
- All of flip-flops in a register are controlled by the same clock signal 
  Drawn at a higher level of abstraction
- Input and output pins that are not single bits are labeled with a slash and number of bits and drawn as a heavier line than the single bit wires and are called *buses*
- Ripple full adders can also be represented as a block and both of them can be used to represent larger bit counters

### Registers with Enable
- We might want a register to hold a value for longer than just one clock period
- Add a multiplexer to choose to store a new value or the value already in the flip-flop, since there is no way to stop clocking the flip-flops reliably
- Selection signal in this multiplexer is called "enable"
	- EN = 0, keep current state
	- EN = 1, switch to next state

### Memory concepts
- Memory has locations where data is stored
- Each location has a unique address
	- M-bit number that specifies which of the 2^M locations to access
	- Stores a single N-bit word (where N is number of bits referred as a data size of memory)
	- All bits are accessed simultaneously
- Capacity of memory is the total number of bits it can store (2^M * N)
- Only one location can be accessed at a time in scope of the class
- Write enable signal (WE) controls whether addressed location should be read from or written to
- Writing to a location updates its storage elements to new value with prior information lost
- 
- Memory is array of registers
- Indexing into array by specific register's address
- To write, supply address, data to be written,m and set WE to 1
- Reading value from a particular register requires supplying the address of the location of that register and setting WE to 0

### Memory example
- A memory of 4 locations, each storing 3 bit numbers can be represented as a rectangle with 3-bit bus DI, 2-bit bus A for the address, WE and 3 bit bus for DO

- Inside are 4 registers with following structure:
 ![[Pasted image 20250708134441.png]]