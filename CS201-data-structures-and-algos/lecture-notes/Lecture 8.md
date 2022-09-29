# Lecture 8 - 21SEP22
## Midterm notes
Exam will cover through this lecture. 

Exam is Wednesday 9/28

60 minutes, in class

1 double-sided reference sheet (8.5x11) typed

Short answer problems, reason about algorithms, data structures, reading code, single expression/line of code.

No long code blocks.

Example problems will be released over the weekend.

There will be three midterms total (E1, E2, E3) and a three-part final (F1, F2, F3)

Overal exam grade is as follows:
`AVG( max(E1, F1), max(E2, F2), max(E3, F3) )`

## Lecture notes
Q: What are the two most fundamental resources on a computer?
A: Processor cycles, memory

Q: What are processor cycles?
A: Number of calculations per second that a machine can perform.

Q: Give three examples of memory.
A: RAM, cache, HDD/SSD

### Understanding effeciency machine-independently
*N* will be the size of the input:
1) Count T(N) = number of *constant time* operations in the code as a function of *N*
2) Reason about how T(N) grows when N becomes large

Q: What is constant time?
A: Running time does not depend on the size of the input.

### Constant time operations:
- index into an array
- arithmetic
- comparison (`<=, <, ==`, etc)
- access an attribute of an object (`.length`)
- ArrayList `.get(), .size(), .add()`
- HashMap/Set `.get(), .put()` (amortized constant time)

### Why Big-O Notation 
Q: Big-O notation is an example of:
A: Asymptotic notation

We ignore coefficients and lower order terms (ignore x terms if x^2 exists, etc)

Expected on exam:
- Given an algorithm, determine Big-O runtime complexity
- Given a Big-O runtime complexity, be able to reason about scalability/timing in practice

### Big-O Notes
Can drop any constants; 1N = 100N = 1,000,000N

Can drop lower order terms that are not constants; 4N^2 + N = N^2, 2^N + N^2 = 2^N

### Hiearchy of common complexity classes (make flashcard)
1) O(2^N) - exponential
2) O(N^3) - cubic
3) O(N^2) - quadratic
4) O(N log(N)) - nearly linear
5) O(N) - linear
6) O(log(N)) - logarithmic
7) O(1) - constant

Q: Define *intractible*
A: So inefficient that it is effectively impossible to solve

### Finding Big-O from code
For each line of code, find complexity of each line and count how many times that line will be executed given the size of the input. Add all lines, and you'll get a polynomial or a single term answer.

*Note*: Not all loops increment by one every iteration. `for (int i<0; i<100; i *= 2`. This will impact how many times the line will run, and thereby the runtime complexity. \[this example is O(log(N)) \]

Remember to account for non-constant operations inside of a function. Method calls are usually the culprit here. `ArrayList.contains()` loops over whole list at every call, for example.