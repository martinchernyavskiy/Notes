## Definition:
*Arrays are fundamental data structure in programming which is use to store multiple values in a single variable*

```python
array = []
array.append(1)
array.append(2)
```

```Java
String[] array = new String[3];
array[0] = "First";
array[1] = "Second";
array[2] = "Third";

String[] animals = new String[] {"Dog", "Cat", "Elephant"};

Integer[] numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
```

# Java
## Notes:

- Fixed size
- Can create shadow array to expand
- Contiguous
## Complexity:

- Random Access - O(1)
- Traverse - O(n)
- Remove from beginning O(n)
- Remove from the end O(1)