# Lecture

## Networking
?
- NIC (network interface controller/card)
	- Able to connect computer to different physical mediums: Ethernet and Wi-Fi
	- Every NIC comes with unique MAC (*media access control*) addresses
	- 28 trillion possible addresses
	- Some devices dynamically change MAC addr for privacy
	- MAC address consists of 48 bits total (split into manufacturer and device ID)
<!--SR:!2025-10-11,15,290-->

## IP Address
?
- Command in linux
- Lists 2 interfaces:
	- Loop back interface (allows for creation of network for device to itself), virtual
	- ens4 interface, physical
<!--SR:!2025-09-30,4,272--> 

## Networks
?
- A network has nodes that send bytes to other nodes by MAC address
	- Nodes are computers / switches etc.
	- Either directly or forwarded by switches
- Computers can have multiple NICs
	- Can be on multiple networks
- Use same physical tech (Wi-Fi, Ethernet, etc.)
<!--SR:!2025-09-30,4,272-->

## Routers
?
- We can't send MAC addr to another network without NIC there
- Connect networks together to form internets
- Global internet is the "Internet" we use
<!--SR:!2025-09-30,4,272-->

## Packet Forwarding
?
- Packets (which are some bytes with address and other info) can be forwarded along path from point A to point B (using routers and switches)
- Routers contain forwarding tables that help to decide which direction to send along a packet
	- Such tables would be too big if a router had to know where every MAC existed in the internet
<!--SR:!2025-09-30,4,272-->

## Internet Protocol (IP address)
?
- Used to send packets across internet
- 4 billion possible IP addresses (IPv4), where IPv6 are 4x longer
- Forwarding tables only need to know which way to send for a given network number (ip address is 4 bytes total where part of it is that network number and another part is the unique ID)
- 127.0.0.1 is the loopback interface
<!--SR:!2025-09-30,4,272-->

## Private Networks
?
- Don't have enough IPv4 addresses
- Don't want every machine to be able to receive packets from anywhere
	- Can be divided into subnetworks to create different networks in a bigger org
- Creates individual networks within large organization
<!--SR:!2025-10-11,11,272-->


## Network Address Translation
?
- NICs can have internal and external IP, eg. Google Console
	- *Firewall* can limit what traffic is allowed
	- External IPs are *ephemeral*, meaning they change upon reboot. But can rent static IPs that don't change
<!--SR:!2025-09-30,4,272-->

## Port Numbers
?
- Specify the process since computers may run multiple on the same network
<!--SR:!2025-09-30,4,272-->

## Running a server on GC
?
- Use educational credits to set up a server and configure SSH keys
- Configure firewall
	- Setting IP ranges to all 0 allows for anyone to access the server
	- tcp are the accessible ports
- `python3 -m http.server -d ./A -b 10.128.02 5400 &> A_out &`
<!--SR:!2025-10-14,14,292-->

## Transport Protocols
?
- *UDP*: User Datagram Protocol
	- Don't do any extra work
		- Live streaming
- *TCP*: Transmission Control Protocol
	- Saves and reassembles packets in order to provide original message
	- Packets may be dropped, reordered, split
- Both build on IP networking and provide port numbers
- -tlpn, t is for tcp and u is for udp
<!--SR:!2025-10-10,10,272-->

## Network Stack
?
- *Applications are built upon layers to provide additional functionality*
- TCP or UDP (IP Address + Ports)
- Internet Protocol (IP Address)
- Ethernet or Wi-Fi (MAC address)
<!--SR:!2025-09-30,4,272-->