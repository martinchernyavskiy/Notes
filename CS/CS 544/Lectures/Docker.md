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
<!--SR:!2025-11-14,42,292-->

## Docker
### Registries
?
- Docker registries (DockerHub for example) are places where people upload their docker images
<!--SR:!2025-10-06,14,292-->

### Images
?
- Snapshot of installed software from which to create container
<!--SR:!2025-10-07,15,292--> 

### Containers
?
- Lightweight alternative to VMs
- Allows for distributed system ecosystem on a single machine
- Linux sandbox in which to run process
<!--SR:!2025-10-06,14,290-->

### Dockerfiles
?
- Steps to run in a container
- Used to create new images
- Allows for reproducibility
- Have root privileges by default
```Dockerfile
FROM ..starting point
RUN .. during the build of an image
COPY
CMD .. default commands to run when running a new container
```
.
```Dockerfile
FROM ubuntu
RUN apt-get update && apt-get install -y unzip python3-pip
RUN pip3 install pandas --break-system-packages

COPY hello.py /hello.py 
CMD ["python3", "/hello.py"]
```
- building image first time may take awhile, however building image second time doesn't since docker building caches various layers
<!--SR:!2025-10-08,16,292-->