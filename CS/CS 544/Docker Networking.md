## Interfaces and Ports
?
- Have laptop with NIC and virtual machine with its other IFs
- The VM has 2 docker containers running in detached mode which have same virtual port
	- Each container runs a jupyterlab which is a type of server and listen on port 80
- Goal to open up jupyter on own laptop and communicate with one of the containers
```Bash
docker run -d -p 127.0.0.1:300:80 myimg
docker run -d -p 127.0.0.1:400:80 myimg
```
- Forwards traffic from one NIC of VM into one of the containers
- First 2 parts of the ip address and port number of one of the NICs of the VM. Must have different ports on the outside on VM
.
- SSH is used to send commands or forward network traffic
- 