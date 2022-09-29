# Lecture 7 - 19SEP22
## Runtime efficiency
### String concat
Both `+=` and `StringBuilder.append()` both concat strings

The `+=` is in *quadratic complexity*, but `StringBuilder.append()` is in *linear complexity*, making it exponentially more efficient.

Averaging out each call of both methods of string concat, the `+=` operator increases with number of times used, making it *greater than linear* time complexity. That's because the character array under the hood has to be copied every time, and the number of characters in that array is growing.

But `StringBuilder.append()` takes less or similar time with an increase in method calls, making it *at most* linear time.

Q: What is a *String* in java?
A: An immutable array of characters.

Q: What is a StringBuilder?
A: A mutable container to characters

Q: What BigO is quadratic time?
A: O(n^2)

### How StringBuilder works
Similar to *ArrayLists*

Creates an oversized array, and doubles in size every time its capacity is nearly full, reducing the number of character copies required through iterations. This comes with a memory tradeoff.

### Algorithm Design
For *O(NM)*, doubling both results in a 4x increase in runtime; if N >> M, still doubles.

For *O(N+M)*, doubling N and M doubles the runtime; if N >> M and we double M, there is little difference in runtime

### Practice/ Example
[Leetcode Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)

