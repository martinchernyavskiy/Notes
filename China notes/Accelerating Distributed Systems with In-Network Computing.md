- Wenfei Wu

### Distributed Systems
- Moore's Law slowing
- Need for higher computation power
- Distributed systems are hard to scale

### In-Network Computing
- Offloads application functions to. network devices
- Benefits inlcude:
	- High throughput
	- Sub-RTT latency
	- High computation speed


### INC architecture
- Changes network architecture


Traditional networks:
- Need a layered architecture which evolves independently, support the Internet ecosystem, but is not efficient


- Trend of large clusters
	- Everything belongs to a single party (no ecostystem)
	- Each layer is programmable
	- Promotes efficiency

### Need new infrastructure for this ecosystem
- Separate application-network codesign
- Build universal libraries for developers
- Build new devices for INC


### Accelerating Machine Learning (ASPLOS23, NSDI21)


- #### Learning algorithm
	- Each iteration computs a gradient
	- Updates the model
	- $W^{t+1}:= W^t - \alpha \nabla J(W^t, D^t)$
- #### Distributed Training (data parallel)
	- Each workers computes a gradient
	- Aggregate all workers' gradients and send result back (AllReduce)
	- Work updates model

