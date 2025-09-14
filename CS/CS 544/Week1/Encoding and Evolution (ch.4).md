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

## Packet Forwarding
- Packets (which are some bytes with address and other info) can be forwarded along path from point A to point by (using routers and switches)
- Routers contain forwarding tables that help to decide which direction to send along a packet
	- Such tables would be too big if a router had to know where every MAC existed in the internet

## Internet Protocol (IP address)
- Used to send packets across internet
- 4 billion possible IP addresses (IPv4), where IPv6 are 4x longer
- Forwarding tables only need to know which way to send for a given network number (ip address is 4 bytes total where part of it is that network number and another part is the unique ID)