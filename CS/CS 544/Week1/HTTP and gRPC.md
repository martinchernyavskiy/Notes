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
- POST: create new resource 
- PUT: update a resource
- GET: fetch a resource
- DELETE: delete a resource
- others...
- REST API (application program interface) provide ability to use the http methods using official APIs from servers

## gRPC
?
- RPC: remote procedure calls
	- procedure is a function
		- when call function from same computer, this is called a regular procedure call
		- when call function from other computer, this is called remote procedure call
	- We use remote since the server might have faster hardware and/or access data not available directly to the client