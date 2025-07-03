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