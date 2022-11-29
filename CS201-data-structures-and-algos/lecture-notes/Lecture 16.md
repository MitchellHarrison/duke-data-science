# Lecture 16 - 02NOV22
## Greedy Algorithms

### Optimization problems
Find a maximium or minimum solution among a set of possible solutions

#### Knapsack problem
Have a knapsack full of items, each has a value and a cost.
Find the most value you can get given a specific budget.

### Greedily searching for optima
Start with partial solution; at each iteration, make a step toward a complete solution

Q: What is the *greedy principle*?
A: In each iteration, make the lowest or highest value step.

For knapsack, a partial solution is a set of items that you can afford at all.
Greedy step: add the next best value/cost ratio item in that set.

*There is no guarantee that greedy algorithms will find a global optima!*

### Why learn greedy algos?
They are the optimal solution for many problems.
Aren't provably optimal, but often works well in practice.
They can be quick to implement.
Often the best way to get started designing an algorithm.

### Aside: What is machine learning?
Models are often trained with gradient descent, which is a greedy algorithm. That's why there is a global minima/maxima problem in machine learning.

### VoteRigging APT
Given votes for candidates, that is an array of integers, and you want to move votes from other candidates to candidate 0.

Greedy decision: move votes from candidate with the most votes.

Runtime is **O(RN)**, where *R* is the minimum number of votes needed to move.

This could be made slightly more efficient using a priority queue that keeps the number of votes each candidate has. This would have **O(Rlog(N))** runtime complexity, notwithstanding the time it takes to add values to the queue.

## P5 - Huffman compression
Q: What is *compression*?
A: Encoding data with fewer bits to use less memory

### Encoding
Eventually, everything will be represented as a bit sequence: `01101010110101100...`

*Fixed-length encoding* stores each value in a unique bit sequence of the same length stored in a table.

With *N* unique values to encode, you need $log_2(N)$ bits per value for fixed-length encoding.

### Optimize encoding
Suppose we have three characters : `{a, b, c}`
A appears 1,000,000 times, and b and c occur 50,000 times each

Fixed-length encoding would use 2,200,000 bits: ($log_2(3) = 2$ and $2 * 1,100,000 \text{ characters} = 2,200,000 \text{ bits}$ 

Variable length encoding can vastly shrink that memory requirement.

Q: What is the *prefix property*?
A: in variable-length encoding, if one bit sequence is the prefix to another, you can't know which one to use

