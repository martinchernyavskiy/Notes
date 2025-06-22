### Logic Circuits
- Made of logic gates, which are made of transistors, connecting each output to power or ground based on the design of the circuit and the voltage level of each input 
- We focus primarily on the boolean representation of the inputs values and boolean results

### Role of Transistors
- Acts like a microscopic switch, either allowing or disallowing current to flow, depending on the voltage of its input
- Can be in series (row) (and) or parallel (or) (not acting on each other)
- FET (field-effect transistor) is a transistor that is controlled by a voltage
	- N-type FET
		- Input "1" makes it a closed switch, making electrical connection between its two other terminals
		- Input "0" makes it an open switch, disconnecting those terminals
	- P-type FET
		- Input "1" disconnects terminals
		- Input "0" bridges the terminals

### Logic Gate
- Electric circuit that contains transistors that connect the output to power or ground based on the input voltage(s)
- Power = voltage as logic 1
- Ground = voltage as logic 0


### Designing Logic Circuits
- More abstract than devices abstraction layer, hence we worry about only the boolean values
- Logic gates correspond to basic boolean operations

### Types of Logic Gates
- NOT gate = inverter (triangle with bubble)
	- Made of PFET and NFET. If input is 0, PFET connects the output to the power supply voltage, while NFET is not conducting. If input is 1, then it's the opposite and NFET connects output to ground
- AND gate (elongated capital D)
- OR gate (3 curved sides, sharp shield-like)
- XOR gate (similar to OR but additional curved line on the input side)
- Note: Boolean variables are actually voltage signals sent from gate to gate over wires, so logic function is itself a signal
- Points at which the wires connect to the gates are called pins
- Gates that are complements of basic operations have same symbols, but with a bubble

### Combinational Circuits
- Logic circuit whose output depends only on the current values of its inputs, not any past behavior