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

### Complex I/O devicds
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
- Tr