# Lecture 18 - 09NOV22

For balanced BST, `.search()` is **O(log(N))** 
For perfectly imbalanced BST, `.search()` is **O(N)**

## Red-Black trees
*Red-black trees are BST's that implement the following*:
- satisfies all properties of BST's
- every node is red or black
- the root is black
- red node cannot have red children
- `null` is considered black
- from a given node, all paths to `null` should have the same number of black nodes

*Why*?
- We know how to re-establish the RBT invariants in **O(N)** time.

Any RBT with *n* nodes has height **O(log(N))**
