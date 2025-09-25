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
- SSHDemon program runs on VM which is a server that's looking for incoming connections from SSH client
	- Uses port 22 by default

## SSH Tunnel
?
- `SSH USER@VM -L localhost:5000:localhost:300`
	- *Allows to forward traffic along (port forwarding)*
	- Normally ssh program is a client on laptop, but by tunneling we are able to make it act as a server, thus listening to requests.
	- Same happens to sshd (sshdemon) that will also act as a client and not just a server
- Any packets coming to lo on port 5000, ssh will see those and send them to sshd sends those to port 300
- *Security*
	- If we don't specify the the IP address in docker run command, then it defaults to 0 and anyone from anywhere can talk to port 300 of the VM and run code inside the jupyterlab
- Port forwarding nevers goes to lo inside container
	- Instead use 0.0.0.0 inside container

### Demo
```Bash
pip3 freeze > requirements.txt
```
.
```
Dockerfile:

FROM ubuntu:24.04
RUN apt-get update && apt-get install -y python3 python3-pip curl iproute2
COPY requirements.txt /tmp/requirements.txt
RUN pip3 install -r /tmp/requirements.txt --break-system-packages
CMD["python3", "-m", "jupyterlab", "--no-browser", "--ip=0.0.0.0", "--port=7], "-allow-root", "--NotebookApp.token='"]
```
.
```
docker build . -t jupyter
docker run -d -p 127.0.0.1:13:7 jupyter
```

## Docker Compose 
?
- *Orchestration*: allows to deploy many cooperating containers across a cluster of Docker workers
- *Kubernetes (K8s)*: most well known orchestration
- *Docker Compose*: simpler tool to deploy cooperating containers to a single worker
- yaml is basically a nicer json
```Docker
vim docker-compose.yaml

services:
	counter_service:
		image: counter
		ports:
			- 5000:5440
		deploy:
			replicas: 3
```
- docker compose up

## Data Placement
?
- *Partitioning*: breaking up a data set so that multiple machines can focus on part of it
- Should we have multiple *replications* of the same data so that we don't lose information if machine fails?
	- *Simple partitioning*: split up by half directly, however might not know which computer to ask for a given name.
	- *Range partitioning*: have a set range, easy to know where to find a given name, hard to find a good split point
	- *Hash Partitioning*: choose key column and then hash it, hash function returns arbitrary number for any input. 