# Lecture 19 - 14NOV22
## Graphs
Q: What are *vertices* or *nodes*?
A: Represents an item in a graph

Q: What is an *edge*?
A: The connection between two vertices in a graph.

Q: What are *cycles* in graphs?
A: Closed rings of connected nodes.

Q: What are *undirected graphs*?
A: Edges can be traversed in both direction

Q: What are *directed graphs*?
A: Edges go one way only

Q: What is a *simple graph*?
A: A graph with at most one undirected, or two directed, edges

#### Notations
`N` or `|V|` = number of vertices/nodes
`M` or `|E|` = number of edges

**Note:** $M \le N^2$ for a simple graph

Q: What are *disconnected graphs*?
A: Graphs with nodes that cannot be reached from other nodes.

Q: What is a *path*?
A: A sequence of edges with unique vertices

**Note**: paths are directional. Going the opposite direction down a path is a different path

### Depth first search (DFS)
Q: What is *depth-first search*?
A: Recursively backtracking to the last node from which you could have taken a different path and trying another.

Tree traversals assume a maximum of two child nodes with no cycles
Graphs handle more adjacent nodes, with cycles being possible

##### Base Cases
Must keep track of the set of previously visited nodes, and stop iterating if reaching one of those
Must return if trying to traverse off the map. 

##### Runtime Complexity
Suppose graph is NxN grid
Each node is recurrsed on $\le 4$ times, since each has a max of 4 neighbors
Each recursive call is **O(1)**
Overall runtime complexity is **O(N)** where *N* is the total number of nodes.

### Iterative DFS
We can use iteration and a `stack` to perform DFS
The CPU uses a stack when recursing, the *call stack*.
In this case, we simply use a stack of our own, instead of using the CPU's

#### Adjacency
Q: What is an *adjacency list*?
A: A map with keys of all vertices, and values containing a list of all nodes with edges between them with that key

Q: What is an *adjacency matrix*?
A: An NxN matrix where each row and column represent a node, and a `true` wherever there is a node between the row and column node, not including itself
