# Lecture 14 - 19OCT22

## Comparitor review
Implementing comparator on `Person201` Objects:
```java
import java.util.*;

public class Person201Comparator implements Comparator<Person201> {
	@Override
	public int compare(Person201 p1, Person201 p2) {
		int sameBuilding = p1.building.compareTo(p2.building);
		if (sameBuilding != 0) { // in the same building
			return sameBuilding;
		}

		int floorComp = p1.myFloor - p2.myFloor;
		if (floorComp != 0) {
			return floorComp;
		}

		return p1.getName().compareTo(p2.getName());
	}
}

// other file
public static void main(String[] args) throws IOException {
	Person201[] people = {}; // insert array of people here
	Arrays.sort(people, new PersonComparator()); // use comparitor
}
```

## Runtime of sort and comparitor
`Arrays.sort()` and `Collections.sort()` are **O(CN log(N))** where *C* is the runtime efficiency of the `.compareTo()` method.

Runtime to sort *N* `ArrayList` objects, each with *M* elements is **O(MN log(N))** 

#### Exam Note: 
We will be asked to compare `.equals()` methods on strings. Bear in mind that, given relatively small, constant-length strings, `.equals()` is effectively **O(1)**

## Binary Search
Given a *sorted* list of N elements and a target, in **O(log(N))** time, find the value in a list

Works by splitting list in half, `low` represents the floor and `high` represents the ceiling to be searched. We must maintain these invariants throughout the search.

Cut search space in half at every iteration, hence **O(log(N))**

To split the list, we take the element in the center of `0` and `N-1` at the beginning, and that new element becomes either `low + 1` or `high - 1` (correcting for the middle element not being the one searched for) depending on whether or not it is greater than or less than the element being searched for.

The search is terminated early if it happens to land on the element being searched for when finding midpoints.

Binary search doesn't guarantee which match you will get if there are duplicates of the element you are searching for.

## P5 Autocomplete
Searching for all words that match on a prefix, sorting them by how common they are
return these words and show in GUI

## Stacks and Queues
### Stacks:
Last in, first out (LIFO)

Like a stack of paper, the most recent one you place on top is the first one you grab.

`.push()` adds to the top, `.pop()` takes from the top and removes it from the stack

Java has a `Stack` class in `java.util.Stack`

`.push()` and `.pop()` are **O(1)**

`.peek()` checks the value on the top of the stack without removing it

Stacks are used for things like the web browser back button, Java call stack, depth-first search in a graph (more info soon)

### Queues:
First in, first out (FIFO)

Like a line into a club, the first person in line is the first person in the building

**TODO check that these are the correct names. Push/pop?**
`.enqueue()` adds an element, `.dequeue()` removes one from the front

Java has `java.util.Queue`, but it's an interface, not a class

i.e: `Queue<String> myQueue = new LinkedList<>()` (Linked lists are an implementing class)

Also has a `peek()` method

Queues are used for waitlists, processor cycle allocation, etc.

### Priority Queue:
Queue, but ordered by their *priority* and not their value

Priority is assigned by some arbitrary code while being inserted into a queue

Java has `java.util.PriorityQueue`

Elements are removed smallest-priority first

