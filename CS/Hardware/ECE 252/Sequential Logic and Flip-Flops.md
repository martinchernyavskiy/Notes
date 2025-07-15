  

### Combinational Circuits
- Outputs depend only on current input values
- Don't know anything about the past information
- No stored information

### Sequential Circuits
- Keep past information as memory
- Only key information is enough that is specific for a particular machine
- Variety of structures used in digital circuits to store a single bit of information

### D flip-flop

[](https://github.com/martinchernyavskiy/Notes/blob/353bda4cad2c47cbf9cd27125c8445b46420577e/CS/Hardware/ECE%20252/Sequential%20Logic%20and%20Flip-Flops.md#d-flip-flop)

- One bit data input, one bit data output, and a special input called "clock" that controls when flip-flop can store a new value

### Clock Signal

[](https://github.com/martinchernyavskiy/Notes/blob/353bda4cad2c47cbf9cd27125c8445b46420577e/CS/Hardware/ECE%20252/Sequential%20Logic%20and%20Flip-Flops.md#clock-signal)

- Signal that oscillates between 1 and 0 at a specific frequency (Hz, or cycles per second)
- Clock period is the time it takes for a single cycle
- Flip-flop can update its stored value only on the positive (rising) edge of the clock signal

### Flip-Flop Behavior

[](https://github.com/martinchernyavskiy/Notes/blob/353bda4cad2c47cbf9cd27125c8445b46420577e/CS/Hardware/ECE%20252/Sequential%20Logic%20and%20Flip-Flops.md#flip-flop-behavior)

- D flip-flop updates when the clock transitions from 0 to 1, thus it's edge sensitive
- Current state: value currently stored in flip-flops
- Next state: value that will be stored at the next triggering clock edge

### Finite State Machines

[](https://github.com/martinchernyavskiy/Notes/blob/353bda4cad2c47cbf9cd27125c8445b46420577e/CS/Hardware/ECE%20252/Sequential%20Logic%20and%20Flip-Flops.md#finite-state-machines)

- Machine that has a finite number of states, thus sequential circuit is this type of a machine.
- State of the machine is its current status (contents of flip-flops)

### State Diagram

[](https://github.com/martinchernyavskiy/Notes/blob/353bda4cad2c47cbf9cd27125c8445b46420577e/CS/Hardware/ECE%20252/Sequential%20Logic%20and%20Flip-Flops.md#state-diagram)

- Represents possible states of the machine and transitions between them
- Represented by a circle where N flip-flops represent 2^N different states