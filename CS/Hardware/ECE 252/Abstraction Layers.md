*Used for managing complexity which allows to design more and more complex systems and software. Allows for specialized teams to focus on designing one part and not the whole thing.*


## Categories:
?
- ### Software
	Analogous to the UTM's "description of required behavior", representing a way to control the hardware to perform whatever computations are needed.
- ### Hardware
	Physical part of the computer, we focus on the [[processor]] part.
<!--SR:!2025-06-21,3,250-->

## Abstraction levels:
?
- ### Problem statement
	Human language description of what needs to be done using a computer, the main problem of interest
- ### Algorithm
	Procedures used to perform a particular task, not specific to a particular processor or programming language
- ### Program
	Realization of problem statement, implemented in a particular programming language, implementing algorithm(s).
	Languages are split into two types: low-level and high-level. 
	Low-level is closely tied to computer hardware and instruction set.
	High-level is more abstract from hardware and is more portable across different systems.
	Compiler translates high-level programming languages into machine code.
	Assembler translates low-level language into machine code.
- ### Instruction Set Architecture (ISA)
	Lies at the boundary of abstraction and specifies the hardware capabilities and how it can be controlled by software.
	Each different ISA defines a particular "machine language". If software is written to speak that language, then it can control any processor designed to listen to it
- ### Microarchitecture
	High-level organization of a processor, determining number of logic circuits, special hard-ware based circuits
- ### Logic Circuits
	Determines the type of circuits to use to accomplish a computation. Designers create structures out of small building blocks, called logic gates, which operates on 1s and 0s, each of which contain multiple transistors. These logic gates produce 1s and 0s as their outputs based on the 1s and 0s as their inputs. (voltage levels are represented with symbols 1 and 0).
	Using logic gates, we can build logic circuit for a specific single function, but there are multiple ways to do so which is a choice of design in the logic circuits layer
- ### Devices
	Lower-level details where designers need to think analog again.
	Focus on transistors that respond to voltage levels.
	Relationships between voltage, current, power, speed, and heat, as well as other details.
<!--SR:!2025-06-21,3,250-->


## Key theme:
?
- Transition between abstraction layers, starting at the top and traverse to the bottom.
- Compiler itself a program is the one that converts program to sequences of binary values, representing single small step to be executed by the processor. It is a program that runs on the processor itself and is designed based on the ISA
- Hardware description language (HDL) is used to describe the hardware and extensive simulation tools are used to test hardware before moving to the devices layer.
- The transformation to the device level is done with complex computer-aided design software tools, implementing processors with billions or more transistors.
- These tools have enormous computational and memory requirements that manufactures use dedicated server farms
- ![[Pasted image 20250618115613.png]]
<!--SR:!2025-06-21,3,250-->