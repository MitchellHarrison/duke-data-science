# Lecture 12 - 12OCT22
## Recursion
Q: What is *reursion*?
A: An algorithm is defined by calling itself

Q: What is the *base case*?
A: A problem is so small that you can solve without any recurssion?

Q: What is the *general case* (aka *recursive case*)?
A: The case where it is necessary to call a recursive function to solve a problem

### Demo Recursion
```java
public int size(ListNode list) {
	if (list == null) return 0; // base case
	return 1 + size(list.next); // general case
}
```

### The Call Stack
Each method call gets its own *frame*.

Q: What is a *frame*?
A: Space in the CPU where a method call is executed.

Q: What is the *stack*?
A: Ordered list of frames that allows the CPU to track the order of execution.

`main` method will have its own frame on the stack, and each method call will have its own frame that returns to the `main` frame, unless it branches off into another method call.

### Notes
Recursion will occur until the base case is arrived at, then every frame returns back to the frame that first called the recursive method.

Q: What is the runtime complexity of an *insertion sort*?
A: $O(N^2)$

The `myString.compareTo()` method helps order strings. Returns negative if it comes before what is passed, positive if it comes after, and 0 if they're identical.

#### Building recursive algos
1) consider base case first
2) check with small problem, one or two calls.
3) generalize from N nodes, trust N-1 nodes

#### Recursive runtime
Q: What is a *recurrence relation*?
A: $T(N) = a*T(g(N)) + f(n)$

- T(N) -> runtime of method with input size N
- a -> number of recursive calls
- g(N) -> how much input size decreases on each call
- f(N) -> runtime complexity of non-recursive elements

**Note**: solving recurrence relations is not part of this course, but stating a recurrence relations might be (common solutions to recurrence relations will be provided via table)

### Merge Sort
Base case: list is size 1, return list

Recursive case: 
- MergeSort(firstHalf)
- MergeSort(secondHalf)
- Merge the sorted halves
- Return sorted

Q: What is the runtime complexity of merge sort?
A: $O(Nlog(N))$

Why $O(Nlog(N))$?
- halves at each level, so log(N) levels
- **TODO**
