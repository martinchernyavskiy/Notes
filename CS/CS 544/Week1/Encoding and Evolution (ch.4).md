# Lecture

## Networking
?
- NIC (network interface controller/card)
	- Able to connect computer to different physical mediums: Ethernet and Wi-Fi
	- Every NIC comes with unique MAC (*media access control*) addresses
	- 28 trillion possible addresses
	- Some devices dynamically change MAC addr for privacy
	- MAC address consists of 48 bits total (split into manufacturer and device ID)

## IP Address
- Command in linux
- Lists 2 interfaces:
	- Loop back interface (allows for creation of network for device to itself), virtual
	- ens4 interface, physical 

## Networks
- A network has nodes that send bytes to other nodes by MAC address
	- Nodes are computers / switches etc.
	- Either directly or forwarded by switches
- Computers can have multiple NICs
	- Can be on multiple networks

## Routers
- Connect networks together to form internets
- Global internet is the "internet" we use