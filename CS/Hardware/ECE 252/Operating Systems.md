### OS definition
- Software serving as an intermediate layer between application software and the system hardware 
- There are variety of different operating systems and some are used in embedded systems

### OS advantages
- Provides services to applications
	- IO services
		- OS handles all direct contact with the I/O devices
		- Applications request OS to perform some action for them
	- File system management
		- Creating, reading and writing of files
		- Prevents application from accessing files it should not
	- Communications
		- Application can just request that OS opens a conduit to some remote entity over the network connection, not implement network protocols which are quite complex
- Manages software resources
	- Application scheduling / multitasking
	- Resource allocation and arbitration between applications
	- Error handling
	- Process protection (prevents an application corrupting other applications or the OS itself)
- Manages hardware resources
	- Hardware abstraction
		- Uses low-level software, *device drivers*, that interface between OS and the system hardware
		- Some device drivers are supplied as part of OS, some by manufacturer as hardware component
	- Platform independence
		- Same application software can be used on very different hardware configurations
	- Power management
		- Manipulates processor clock speed per workload
		- Manages power states of attached devices to minimize power consumption

### I/O Services
- Applications can interact with I/O devices without specific knowledge of all of them
	- Instead applications can just ask the OS for services it needs
- All application-level I/O is controlled by and goes through the OS
	- System hardware prevents applications from accessing I/O directly to ensure this

### Communication with the OS
- OS must handle all direct interaction with I/O devices since multiple applications may use them and this may create conflicts
- Applications shouldn't have information / access to OS subroutines. Must be isolated but able to communicate.
	- Must be built into the processor itself so that software can't get around it

### Processor System Call Support
- Processors provide an indirect mechanism for applications to request OS services on hardware level
	- Implemented through special instructions - *software interrupts or TRAPS*
	- Part of instruction includes a number identifying which service is being requested
	- Executing these instructions is called a *system call*
	- Transfers control to OS to perform the service