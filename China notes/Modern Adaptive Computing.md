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