### Domain-Specific Processors
- AntMiner for Bitcoin (processor specifically for it)
- Tensor processing
- VCU for video codec
- Anton 2 for molecular dynamics
- AWS Graviton3
- M4 for macOS
- *Need to develop different processor for different goals*

### Decision for processor
- Software-based simulation
	- ISA simulation (spike)
	- $\mu$Arch simulation (gem5)
	- RTL simulation (verilator)
		- Helps to describe how circuit works
- Hardware-assisted emulation
	- FPGA prototyping 
	- Hybrid emulation platform
	- (ASIC-tapeout)

### FPGA prototyping
- Before manufacturing a chip, we're able to emulate it first
- The architecture of the chip involves fine grain and coarse grain 
- Fine grain:
	- bit-level network of LUTS and FFs
	- combination and sequential circuits
- Coarse grain:
	- world-level network of VLIW PEs

### AI Engine Array
- Array of very-long-inst-word (VIW) cores
- Consists of AI Engines

### Timing and Power
- clock-to-Q
- routing delay; logic delay
- setup time; (hold time)
- (clock skew)
- $P_{tot}=P_{D}+P_{I}+P_{S}$, where 

### Verilog
- "Verification" + "Logic"
- Used to describe use of circuits, originally designed for simulation/verification purposes, but became synthesizable afterwards
- SystemVerilog is the successor
- Synchronous FIFO 
	- Construct module with given depth and data width
	- Include the inputs and outputs 
	- Set default values
	- Code reading and writing data from/to FIFO
	- 
- 