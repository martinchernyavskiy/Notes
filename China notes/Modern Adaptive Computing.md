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


### FPGA vs. ASIC
- FPGA is more flexible, but worse in terms of power
- FPGA is better at NRE, time to market, design flow, barrier to entry
- ASIC is better at performance, cost per unit (high volume), energy efficiency, analog blocks

### CPU vs. GPU vs. FPGA
- GPU has highest computing performance
- CPU has highest development efficiency and low & fluctuating latency
- GPU has high latency and medium development efficiency
- FPGA is in between, has low and stable latency and low development efficiency

### FPGA Application Categories
- Chip design for prototyping
- Telecom 
- Automotive
- Computational Finance
- Medical Imaging
- Datacenters
- Databases 


### FPGA Architecture
- SRAM
- Consists of a sea of logic blocks
- Each of logic block consists of more small blocks with each having a 4-input LUT (look-up tables), mux, and flip-flop
- Each group of logic blocks have outputs connecting to a wire system (routing track) which is regulated by a programmable routing switch

### FPGA design flow
- First use RTL code
- Use logic synthesis for netlist and then place & route to FPGA to generate bitstream & debug and run

### FPGA vs. CPU
- CPU allows only for one instruction to be executed at a time
- Multiple functions can be executed simultaneously in the FPGA