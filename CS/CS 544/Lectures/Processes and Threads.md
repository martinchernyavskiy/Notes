## Threads
?
- Have their own instruction pointers and stacks, but share heap.
- *Single-threaded process*
	- One instruction pointer and one stack
- *Multi-threaded process*
	- Multiple instruction pointers and multiple stacks

## Context Switch
?
- Change which thread a CPU is running (CPU rotates its instruction pointer per state of each thread)
- CPU schedule is a sub system in OS
- Decides when to context switch between threads

## Scheduling Restrictions (Blocked Threads)
?
- Threads can have multiple states
	- Running (CPU is executing it)
	- Blocked (the thread is waiting for something other than CPU)
		- Examples could include waiting on network, input, disk, etc. 
	- Ready (scheduler can make a context switch to it)

## Efficient Use of Compute Resources
?
- if there are not. enough threads or blocked threads, then we aren't utilize the CPU to the max of its capabilities (have idle CPU cores)
- *Multi-threaded applications* are applications that utilize multiple threads which provide efficiency, but may introduce bugs such as race conditions and deadlocks
	- All share same virtual address memory 
- *Multi-process* applications are easier to program and are better of parallel work

## Demo
?
- Some of the thread operations include:
	- t = threading.Thread()
	- t.start(target=????, args=`[????]`)
	- t.join()
	- t.get_native_id()
```python
import threading 

def task() {
	# some function
}

threading.get_native_id()

t = threading.Thread(target=task, args=[1_000_000])
t.start()
t.join() 
```
- threads are different for each function
- gRPC automatically manages threads
- Can't pass in arguments direction into the target function
- Race conditions