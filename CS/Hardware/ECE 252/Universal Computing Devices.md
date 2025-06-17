## Turing Machine

- Proposed by Alan Turing
- Any computable computation can be implemented by some machine 
	- Reads/Writes one symbol on an infinite tape
	- Selects action to perform from a fixed set of rules based on symbol and current state of the machine
	- Elevator example

## Universal Turing Machine

- Can simulate any other Turing machine by inputting a description of that machine's behavior rules
- Programmable computer is effectively a UTM (but finite memory/tape)

## Key Theme

- Given enough memory and time, a computer can compute anything that's possible to compute. However in practice, there are more constraints:
	1. Time
	2. Cost
	3. Power/Energy

## What makes computer "faster"

- Faster "clock" which paces the computations
- More parallel structures, to do multiple things at once
- More complicated hardware, allowing one to do some work in a single step rather than in multiple
- Faster/closer/larger memory structures so it can access data faster and spend less time moving information around before/after computations

## Design trade-offs

- Faster devices require more hardware (cost more and use more power)
- Cheaper devices use less silicon or fit fewer transistors than more expensive ones, so they don't have as much specialized hardware or parallel structures that increase performance)
- Low-power devices cannot have as high clock-rate as high-power devices because of lower voltage which lowers the clock rat