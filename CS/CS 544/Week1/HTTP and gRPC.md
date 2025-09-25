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
	- In client have function that sends code to server (*stub function*)
	- In server have rpc_server that receives code
- *Serialization and Deserialization*: converts information to/from bytes

## Serialization and Deserialization (in-depth)
?
- Serialization converts various types to bytes (wire format)
- Deserialization converts bytes to various types
- *Every language has different types and we want cross-language calls*
	- gRPC uses Google's Protobufs (Protocol Buffers) which provide a uniform type system across various languages
	- Protobufs use variable-length encoding
		- Smaller numbers could use less bytes if not necessary
- *Different CPUs order bytes differently*

## gRPC
?
- Sits on top of HTTP layer


## gRPC demo
?
- We use Aider in p2
- export Gemini api key as an environment variable
- Install aider and launch gemini 2.5 flash (aider-install && aider --model gemini/gemini-2.5-flash)
.
- create python environment and run the following:
```
python3 -m venv venv
source venv/bin/activate
pip install grpcio-tools==1.74.0 grpcio==1.74.0 protobuf==6.32.1 aider-install
```
- .proto file contains messages and services (RPC calls)
	- *Protobuf is used for serialization*
	- messages contain information for variables in request and response
- If the variable index positions differ, then response will ignore the extra variables from request and default the value to 0 for the ones not received
```proto

syntax = "proto3";

// MESSAGES
message MultRequest{
	int32 x = 1;
	int32 y = 2;
}

message ResultResponse {
	int32 result = 1;
}

// SERVICES (RPC calls)
service Calc {
	rpc Mult(MultRequest) returns (MultResponse)
}
```
. We can have a build.sh program to compile math.proto
```sh
#! /bin/bash

set -3

GEN_DIR="."

python3 -m grpc_tools.protoc \
	--proto_path=. \
	 --python_out=$GEN_DIR \
	 --pyi_out=$GEN_DIR \
	 --grpc_python_out=$GEN_DIR \
	 math.proto
	 
echo "math.proto compiled successfully"
```
- Creates math_pb2.py , math_pb2_grpc.py,math_pb2.pyi
	- math_pb2.py is used for serializing and deserializing messages
	- math_pb2_grpc.py provides a servicer (a class to be inherited from) and stub for making remote procedure calls
- math_pb2.py has quite a lot of functions to use such as .MultRequest which saves message variables to a variable. We can use .SerializeToString() to convert the message to bytes.
	- len(s) would then be less than initial variables for the request messsage per *variable-length encoding*
- math_pb2.MultRequest.FromString(s) deserializes the contents of the serialized message and we can assign them to a variable
- Can use aider to generated a server.py to implement math.proto
	- Overrides grpc servicer to apply the right calculation logic'
- For debugging purposes, python3 -u server.py &> log.txt &
	- Force the stdout and stderr streams to be unbuffered
- For implementing client, we write a mult.py that uses Calc stub to ask the server to multiply. It shall use argv to get the arguments