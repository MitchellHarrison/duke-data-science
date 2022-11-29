# Lecture 21 - 21NOV22

### Exam topics
- trees (implemented with array, tree/heap/red-black properties)
- greedy algos, huffman compression
- graphs, DFS, BFS

### Project 6
No analysis required  
Use shared repo on GitLab  
Two parts, graph processor and graph demo.

## Notes
**BFS** is *FIFO* using a queue  
**DFS** is *LIFO* using a stack

### Weighted Graphs
Each edge has a *weight* (also called *cost, length* or *distance*)  
Google maps uses weighted graphs to find the shortest path in time, but we will find shortest by miles  
If normal BFS uses a queue, Dijkstra's Algorithm uses a *priority queue*.  

#### Dijkstra's Algorithm
While unexplored nodes remain:
- explore closest unexplored node
- for each neighbor, update shortest path to neighbor is shorter to go thorugh current  

We may add the same node to the priority queue multiple times using Dijkstra. This (marginally) impacts efficiency, but not correctness.  

Dijkstra is proven to *always* return the shortest path. This is mathematically proved by *induction*.  

#### Runtime
Dijkstra's runtime is **O((N+M)log(N)** with **N** nodes and **M** edges. This is because it considers each node once and each edge twice.
