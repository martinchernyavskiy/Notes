### Input/Output devices
- Aka I/O are devices available in every computer to receive data from outside and produce data to the outside (user)
- Links those devices to their environment

### Examples
- Keyboard : input device (gets information from user)
- Monitor : output device (information is displayed to user)
- But most computers aren't directly used by people, they are embedded into machines instead
- Many devices are capable of both I/O
- *GPIO (general-purpose I/O pin*: pin in computer that can act as a single-bit input or output
	- Can be set to 0 or 1 and thus turn a light switch on or off
	- Can be used as input to check if a button is pressed or not
- Analog-to-digital converter is another example of a common *input* device 
	- Used to convert sound into digital signal
- Digital-to-analog converter is a common *output* device that is used to convert digital data back into sound

### Complex I/O devices
- Network interface 
	- Transfers data to and from remote locations
- Bluetooth radio
	- 2-way radio interface
- USB interface
	- Some can serve as input, some as output, some as both
- Hard drive

### Terminology
#### I/O Synchronization
- *Asynchronous I/O* is not related to the clock
- Since most devices are asynchronous, meaning they work at unpredictable times unrelated to processor clock, there is a need for a processor to check if the device needs service
	- Does keyboard have a character ready?
	- Does the keyboard know that we just read it?
	- This exchange of information is called *handshaking*

#### Unconditional vs Conditional I/O
- Simple I/O devices like GPIO pin driving an LED indicator are always ready to accept or supply new data
	- So processor does a simple transfer of information to the device without checking if it's ready, also called an *unconditional I/O*
- Most I/O devices are *conditional*, so processors need to check if they are ready before transferring or receiving data
	- Check if display is done with processing previous data before sending it more

#### Isolated vs Memory-Mapped I/O
- Information is transferred using special registers in the I/O device's interface
	- *Isolated I/O* is the I/O that is isolated from memory space and thus processor uses special instructions to access the I/O space (which is similar to processor's memory structure)
	- *Memory-Mapped I/O:*
	- Most processors use normal load/store instructions to access I/O devices since the registers are viewed as the same as any other memory locations
		- In order to implement this, some of the locaitons in memory space is set aside and logic is added so that load and store instructions to these addresses access the I/O device registers instead of memory

#### Polled vs Interrupt-Driven I/O
- *Polling*: process of repeatedly checking I/O device register for any data ready to be read
- Most processors however contain hardware support that allows I/O devices to *interrupt* the processor when they need to be serviced
	- When data is ready, device issues an interrupt signal which causes the processor to suspend the program it was executing, switching to execute a section of code that services the device
	- *Interrupt service routine*: subroutine that is invoked automatically by the hardware in response to interrupt signal. When it's finished, processor goes back to execute the rest of the main program

### I/O Device Interface
- Since we're not concerned about the implementation of the I/O devices themselves, we abstract away those details to just use the interface
- *I/O Device Interface is a set of registers of 3 categories*
	- *Status registers*: contain information about the I/O device and are read by the processor
	- *Data registers*: used for exchange of data
	- *Control registers*: registers that affect how the I/O device operates, written to by processors