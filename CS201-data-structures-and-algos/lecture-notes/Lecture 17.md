# Lecture 17 - 07NOV22
## Huffman Encoding
Greedy algorithm for building an optimal variable-length encoding tree

*High level idea*
- Start with leaves/values you want to encode with weights = frequency
- Iteratively choose the lowest weight nodes to connect up to a new root node
- Ties in weights can be broken arbitrarily
- Sum of root node is the summed weight of child nodes

### P5 Outline
Read a compressed file that includes a Huffman Tree
Use that Huffman Tree to decode the document
Write another method to re-encode.

## Binary Heaps
Maintains the *heap property* and *shape property*

The `.remove` operation removes the root and fixes the tree to maintain those two properties.

Java `java.util.PriorityQueue` is implemented with an array (or ArrayList).

*Why?*
- requires less memory (constant, not asymptotic)
- slightly faster
- easier to code

#### Heap Array
*1-based index convention:* (0-based is another)
- first and last index is empty
- left child: index $2k$
- right child: index $2k+1$
- parent: $k/2$ <- *integer division*

*Heap runtimes*
- `.add`: **O(1)**
- **TODO**
