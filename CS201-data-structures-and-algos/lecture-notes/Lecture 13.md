# Lecture 13 - 17OCT22
Q: Which sorting algorithm does Java implement in Arrays and Collections?
A: *Timsort* variant of *Mergesort*

### How Java knows how to sort objects
Class objects must have implement the *Comparable* interface.

Requires implementing the ``.compareTo()`` method.

##### The `.compareTo()` method:
Takes as input another instance of the class.
Returns an integer:
- negative number if `this` comes before the insance passed as a parameter
- zero if `this` is the same as the parameter
- positive number if `this` comes after the parameter

#### Comparable vs. Comparator
`Comparable` interface uses the `.compareTo()` method of an instance of a class.

The `Comparator` is its own class, containing a `.compare()` method that takes two parameters, and sorts those two parameters with each other.

### Notes
Q: What is *natural order*?
A: The default order that `.compareTo()` uses, which depends on the class being sorted.

`Comparitor` has multiple sorting methods:
- `Comparitor.naturalOrder()` sorts in natural order
- `Comparitor.reversed()` sorts in reverse-natural order
- `Comparitor.comparing()` sorts by any given method
	- Ex: `Comparitor.comparing(String::length)` sorts by length of strings instead of alphabetical order

You can supply a comparitor to `Arrays.sort()` or `Collections.sort()` as a parameter, and it will sort using that comparitor instead of natural order.

Q: What is *stability*?
A: The order of elements that are equal by a given sort is not changed, even if they are out of natural order.

Sorting by multiple fields (ie length and then naturally):
```java
Arrays.sort(copy,
	Comparator.comparing(String::length).
	thenComparing(Comparitor.naturalOrder())
)
```

##### Lambda notation in Java
The below snippet uses an arrow to denote a lambda function that sorts by the first element of an array. If `b[0] > a[0]`, then this would be negative, which would mark that `a` comes after `b`.
```java
Comparator<int[]> comp = (a,b) -> (a[0] - b[0]);
```

## Algorithms using sortedness
#### Binary Search
Given a sorted list of N elements, binary search finds an element in O(Nlog(N)) time.

`Arrays.binarySearch(myArray, "a")` or `Collections.binarySearch(myList, "b")` are available if the array/collection that you pass are already sorted.

###### TODO (from slides): can use `Arrays.binarySearch()` with a comparitor