# Lecture 9 - 26SEP22
## Notes
When method chaining, we have to compare both runtime and the size of the output of each method.

For `a(b(n))`, if b returns an `int` of size `n^2`, then we have to find the runtime of `a()` with an input of size `n^2`.

*Steps to find method-chained runtime complexity:*
1) Find runtime of inner method
2) Find output size of inner method
3) Find runtime of outer method given the output of inner method
4) Add the two runtimes together.

## Linked Lists
Implements a list using a *linked data structure*

Have same methods as ArrayLists because they implement the same interface.

Q: What is the advantage of using an array to create a list (*ArrayList*)?
A: It gives a very fast `.get()` method.

Q: What are *nodes*?
A: Entries in a linked list

Q: What is in a node?
A: Data and a reference to the next object in the list

Nodes in a link list could be far apart in memory, unlike with array list.

To `.get()` from a linked list, you have to start at the first element and iterate through all of them in order until you arrive the one you're looking for. Much less efficient than `.get()` in an ArrayList.

Q: What is the runtime complexity of `.get()` in a linked list?
A: O(N) - linear

### Iterating through a linked list using an iterator
First way:
`for (int val : myList) {}`

Enhanced for loop (implicit iterator):
`for `

Explicit iterator: **TODO**
```java
Iterator<Integer> listIter = myList
```

### Why use Linked Lists?
Adding elements to the beginning of the list is a constant time operation. This is also true to adding/removing anywhere, but iterating to the position that you're adding/deleting from is linear.

Q: What is the runtime complexity of adding/removing an element to the front of a linked list?
A: O(1) - constant

Q: What is the runtime of iterating to a specific position in a linked list?
A: O(N) - linear

### DIY Linked-List
The end of the list is the element whose reference to the next element is `null`

Can't call methods on an element containing `null`. It will raise a `Null Pointer Exception`
