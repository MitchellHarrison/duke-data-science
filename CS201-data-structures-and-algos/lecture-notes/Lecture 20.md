# Lecture 20 - 16NOV21
Q: What is a *sparse* graph?
A: A graph where each node is not connected to each other node.

Efficient adjacency "list" frequently uses double hashing, or 
`HashMap<Vertex, HashSet<Vertex>>`

### Graph search data structure
- keep an adjacency list
- keep track of visited nodes in a `set`
- keep track of previous node: "During search, how did I get here?"
- store these things as instance variables of the class containing the search 

### Iterative Depth-First Search
`Stack` will store nodes we have visited/discovered, but not explored from yet.

```java
public static void dfs(char start) {
	Stack<Character> toExplore = new Stack<>();
	char current = start;
	toExplore.add(current);
	visited.add(current);
}
```

Q: What is a *search tree*?
A: A graph with no cycles that corresponds to the path that your search algo found

### DFS runtime complexity
DFS is **O(N+M)** where **N** is the number of nodes and **M** is the number of edges.

Each node is popped once, and considers each edge exactly twice, once from either vertex of that edge. Thus **O(N+2M)** runtime or **O(N+M)**.

## Iterative Breadth-First Search (BFS)
Uses linked lists instead of a stack, so `.add()` and `.search()` is **O(1)**

DFS goes as deep as possible along a path before turning back. BFS explores all neighbors to all nodes that it hits before moving along.

With BFS, the path we find will always be the *shortest path*

BFS: First in, first out exploration
DFS: Last in, first out exploration

BFS uses a *queue* where DFS uses a *stack*
