# Lecture 11 - 05OCT22
## Notes
### Reverse linked list in place
No copying nodes or adding new references/nodes

We'll move one node at a time in a loop

Q: What is an *invariant*?
A: something that is true at the beginning of each iteration

#### Given list \[A, B, C, ...\]
```java
while (list != null) {
	ListNode temp = list.next; // so we don't lose current entry
	list.next = rev; // add next element to beginning of rev
	rev = list; // reestablish invariant
	list = temp; // update list
}
```

### Testing and debugging
Q: What does *UPIC* stand for?
A: Understand, Plan, Implement, Correctness

Q: What is *UPIC*?
A:  A problem-solving process frequently used in computer science

Q: What is *testing*?
A: Verifying that an implementation functions as expected. Given input, check output.

Q: What is *debugging*?
A: A method for finding and fixing specific errors cause a failure in a test

Q: What is *black box testing*?
A: Testing without access to source code.

Q: What is *white box testing*?
A: Testing with access to source code.

More testing cannot guarantee 100% functionality, but more diverse testing should give more confidence.

#### [Website](https://pythontutor.com/java.html) to help debugging visually

### Filling a linked list from an array
```java
list = new ListNode(values[0]);
current = list;

for (int i = 0; i<values.length; i++) {
	current.next = new ListNode(values[i]);
	current = current.next
}
```
