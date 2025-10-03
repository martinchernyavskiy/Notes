## Critical Sections
?
- Code section we don't want to get interrupted
- *Atomicity* (actions taken together, not-disrupted) and *Consistency (invariants)*

## Locks
?
- lock = threading.Lock()
- lock.acquire()
- lock.release()
- Between acquire and release lock is *held* by the thread that acquired it
- *Lock can be held only by one thread at a time*
- *Lock granularity affects the runtime speed tremendously*
	- eg if you lock acquire and release each loop iteration is worse than holding the lock outside of the loop (course grained locking vs. fine grained)
- *Deadlock happens when multiple threads try to acquire multiple locks in a different order. The best practice is for them to acquire locks in the exact same order*

## Locks Demo
?
```Python
bank_accounts = {"x": 25, "y": 100, "z": 200} # in dollars
lock = threading.Lock() # protects bank_accounts

def transfer(src, dst, amount):
    with lock:
    success = False
    if bank_accounts[src] >= amount:
        bank_accounts[src] -= amount
        bank_accounts[dst] += amount
        success = True
    print("transferred" if success else "denied")
    # lock.release() happens automatically even with exception
    
    
transfer("x", "y", 20)
bank_accounts
transfer("x", "y", 10)
bank_accounts
transfer("w", "z", 10) # exception
bank_accounts
transfer("z", "y", 50)
bank_accounts

```

## Python's GIL (Global Interpreter Lock)
?
- Only one thread can be running Python bytecode in a process at once
	- useful for threads blocked on I/O

## Why GIL?
?
- ...

## Challenged Beyond Interleaving
?
- The order of statement execution can be done in a different order by CPU