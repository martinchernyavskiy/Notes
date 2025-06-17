## Definition:
*Arrays(Lists) are fundamental data structure in programming which is use to store multiple values in a single variable*

```python
# Array Initialization
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
// Array Initialization
String[] array = new String[3];

// Adding elements to the array
array[0] = "First";
array[1] = "Second";
array[2] = "Third";

String[] animals = new String[] {"Dog", "Cat", "Elephant"};

Integer[] numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
```

## Complexity:

- Random Access - O(1)
- Traverse - O(n)
- Remove from beginning O(n)
- Remove from the end O(1)# Python

# CPP
## Notes

- 

# Python
## Notes

- Dynamic size acts like array list in Java
- Can contain various types of objects
- Length is the size of array itself, there is no capacity

# Java
## Notes:

- Fixed size
- Can create shadow array to expand
- Contiguous
- Must contain same type of objects 
- Some data structures utilizing array keep a private field to keep track of the size changes as by default there is no way to retrieve that information apart from the total length of the array (its capacity)


## Real World examples

- An engineer at Apple working on image processing algorithms for Iphone cameras might use arrays over files to represent pixel data. Storing images this way makes it easier and faster to perform operations
- A front-end developer at Google working on Gmail might use arrays to manage email threads or conversations. They might even store it as a list of JSON objects with info like author, timestamp, message, receiver, etc.