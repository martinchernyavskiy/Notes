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
		- Application can just requests that OS opens a conduit to some remote entity over the network connection, not implement network protocols which are quite complex
- Manages software resources
	- Application scheduling / multitasking
	- Resource allocation and arbitration between applications
	- Error handling
	- Process protection (prevents an application corrupting other applications or the OS itself)
- Manages hardware resources
	- Hardware abstraction
		- Uses low-level software, device drivers, that interface between OS and the system hardware