## Virtualization
?
- The illusion of private resources provided by software
- Examples:
	- Hardward VMs
		- Virtualized Resources: CPU, RAM, Disk, Network, etc.
		- Can *overbook*: use less resources than provided
		- Each VM contains a copy of an operating system, heavy
	- Language VMs (JVM, PVM, etc.)
	- OS VMs (containers)
		- Shared physical OS
		- Each container contains different "flavors" of Linux
		- *Incompatibility*: Can't have Windows container on Linux
- Virtual Memory

## Docker
### Registries
?
- Docker registries (DockerHub for example) are places where people upload their docker images

### Images
?
- Snapshot of installed software from which to create container 

### Containers
?
- Lightweight alternative to VMs
- Allows for distributed system ecosystem on a single machine
- Linx sandbox in which to run process

### Dockerfiles
?
- Steps to run in a container
- Used to create new images
- 