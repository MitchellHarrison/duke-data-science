# Lecture 22 - 28NOV22
## Minimum spanning tree (MST) problem
Given N nodes and M edges, each with weight/cost, find a set of edges that connect *all* nodes with minimal total cost.  

The result of a MST will be a **tree**, hence the name.  

A **tree** in this case does not mean a binary tree. It is defined, in this context, as any **acyclic graph**, meaning a graph with no loops.  

A **complete graph** has edges from all nodes to all other nodes.  

#### MST examples
- creating a physical computer network using the minimal amount of cabling
- connect several metro stops in a city with the least tunneling.
- image segmentation  

**inductive reasoning** is a way of prove that an algorithm is always correct.

### Prim's Algorithm
- choose an arbitrary vertex
- find a partial solution connecting a subset of the nodes
- choose the cheapest/lowest weight at each step (greedy algorithm step)  

A **disjoint set** of nodes is a collection of nodes, one or more of reach is unreachable from other nodes. This forms a *forest* of trees.  

### Kruskal's Algorithm
Selects the lowest edge that connects two disjoint sets. 

Either disconnected trees or disconnected individual nodes counts as a disjoint set.

**Note:** there may be multiple minimal solutions to MST, but both are equally correct.  

### Kruskals in pseudocode
*N* nodes and *M* edges.  

*S* is a collection of *N* disjoint sets; one per node.  

While S has more than 1 set:  
- (u,v) will be the minimum cost remaining edge.
- Find which sets u and v are in. If not equal:
    - **Union** the sets
    - Add (u,v) to the MST
  
Return the MST

