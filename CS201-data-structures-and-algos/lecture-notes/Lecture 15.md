# Lecture 15 - 24OCT22
## Priority Queue
When removing, you get the highest priority item (which is the lowest number)

Java implents a `PriorityQueue<>()` implementation of the `Queue` interface

### DIY Priority Queue
Invariant: Keep the list sorted
Always remove first (least) node, and update `myFirst`
to add, need to search for correct in-order position

Diadvantage of a simple `LinkedList` implementation of Priority Queue is that the `.add()` operation has **O(N)** time.

### Binary Heap
Priority Queues implented using binary heaps have the following properties:
- `.add()` is **O(log(N))**
- `.remove()` is **O(log(N))**
- `.peek()` is **O(1)**

Each node in a tree contains a reference to a *left child* and a *right child*

Q: What is the *heap property*?
A: Every node is `<=` its successors

Q: What is the *shape property*?
A: The tree is full (every node has both left and right child nodes) except for the rightmost positions on the last level.

## Binary Trees
Why binary trees? Good compromise:
- ArrayLists have fast lookups, but are slow to add or remove.
- LinkedLists have fast add and removes, but slow lookups

Binary Search trees are fast and dynamic: **O(log(N))** search AND **O(log(N))** add/remove

TreeMap/Set vs HashMap/Set:
- Tree is **O(log(N))** add, contains, put, get (not amortized)
- Hash is **O(1)** amortized
- Trees get range of values in sorted order efficiently, while Hash cannot

#### Tree Nodes
```java
public class TreeNode {
	TreeNode left;
	TreeNode right;
	String info;

	// more logic here
}
```

#### Vocab
*Root*: the top node (one with no parent)
*Leaf*: the bottom nodes (ones with no children)
*Path*: sequence of parent-child nodes
*Subtree*: nodes at and beneath a given node
*Depth* of a node is the number of edges from the root
*Height* is the maximum depth of any node

### Binary Search Trees
Not all binary trees are binary search trees

Q: What makes a binary tree a binary search tree?
A: The search property

Q: What is the *search property*?
A: Left subtree values are all less than the nodes values, right subtree values are all greater than the nodes value

#### Efficient search using BSTs
Start at root node, compare with what we're looking for. If that is greater than the value of the root of the tree. If so, we move to right child subtree. If less than, we search left. And repeat.

#### Traversing a tree
This technique using recurssion, like many other operations performed on trees
```java
public void inOrder(TreeNode tree) {
	if (root != null) {
		inOrder(root.left);
		System.out.println(root.info);
		inOrder(root.right);
	}
}
```

To return a list of all values in a tree, a helper method is needed to store the list, which is then passed into the recursive function that appends values to that list.
