## Definition:
*Data structure used to store a sequence of elements. Contrary to arrays which store elements contiguously in memory, a linked lists consists of nodes (a block of memory), where each node contains the data as well as a reference (link) to the next node in the sequence.*

## Benefits

**


## Code snippets

```python
array = []

# Adding elements to list
array.append(1)
array.append(2) 
array.append(3)

# Removes last element of list
array.pop()

array[index] # access element at given index

# Removes element at given index of the list
array.pop(index)

# Slashing 
print(array[1:]) # everything from first index and onwards

# Getting length of the list
print(len(array))

# Getting sum of the elements
print(sum(array))

# Looping through the list
for element in array 
	print(element)

# Prints list in console
print(array)
```

```Java
String[] array = new String[3];
array[0] = "First";
array[1] = "Second";
array[2] = "Third";

String[] animals = new String[] {"Dog", "Cat", "Elephant"};

Integer[] numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
```

## Complexity:

- Traverse O(n)
- Insertion
	- At the head - O(1)
	- At the tail - O(1) if doubly, O(n) otherwise
- Removal
	- Head - O(1)
	- Tail - O(1) if doubly, O(n) otherwise
	- Arbitrary - O(n) since need to traverse to find

# CPP
## Notes

- 

# Python
## Notes

- Dynamic size acts like array list in Java
- Can contain various types of objects

# Java
## Notes:

- Fixed size
- Can create shadow array to expand
- Contiguous
- Must contain same type of objects 
- Some data structures utilizing array keep a private field to keep track of the size changes as by default there is no way to retrieve that information apart from the total length of the array (its capacity)


## Real World examples

- An engineer at Spotify might use a linked list to build a playlist, where each node is a song.
- Users of WhatsApp are able to delete messages, so a linked list could be used to store chat history. Updating the linked list with new/deleted messages and maintaining the chronological order.