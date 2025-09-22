## HTTP
?
- Sits on top of transport layer (URL (domain/IP + port + resource))
	- https:domain:443/cs544/f25/schedule.html
- Client and Server
	- Client sends request to server
	- Server sends response to client
	- Contain header information

## HTTP methods
?
- POST: create new resource (both request and response have body)
- PUT: update a resource (both have body usually)
- GET: fetch a resource (only response has body)
- DELETE: delete a resource
- others...
- REST API (application program interface) provide ability to use the http methods using official APIs from servers

## RPC
?
- RPC: remote procedure calls
	- procedure is a function
		- when call function from same computer, this is called a regular procedure call
		- when call function from other computer, this is called remote procedure call
	- We use remote since the server might have faster hardware and/or access data not available directly to the client
- We need extra functions to make calling a remote function feel same as regular one
	- In client have function that sends code to server
	- In server have rpc_server that receives code
- *Serialization and Deserialization*: converts information to/from bytes

## Serialization and Deserialization (in-depth)
?
- Serialization 

## gRPC
?
- Sits on top of HTTP layer
- 