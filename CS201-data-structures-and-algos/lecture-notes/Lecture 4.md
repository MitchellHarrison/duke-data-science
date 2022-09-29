# Lecture 4 - 07SEP22
## Global Research and Consulting (GRC)
- national organization
- network of alumi
- @grc.duke on insta

## Lecture Notes
- *Abstract Data Types (ADT)* descibes a data types functionality but not its implementation
- *Application Program Interface* describes objects/me

Q: What is an *interface*?
A: Something written into an ADT that an implementing class must override.

Key ADT's:
	- List: ordered sequence of values
	- Set: unordered collection of unique calues
	- Map: key-value pairs


*Lists* in Java are an *interface*, so you cannot create a pure *list* object, only an *implementing class* under the list interface (*ArrayList* for example)
 
Q: What is an *implementing class*?
A: A class that overrides all methods of interface class

This means that implementations have *at least* the same methods as an interface.

### Algorithmic tradeoffs
- intersted in performance at large scale (*n* values)
- **.get()** lookup in an array is *constant time*, or size-independent
- **.contains()** loops through an array and checking for equality at each. Time required grows with size of list.
- **.size()** returns the size of the list in constant time
- **.add()** depends

### ArrayList .add() when used inside of mutable List
1) create an array with extra space
2) add new elements to first open space until full
3) create new, much bigger array and copy original into new one, one value at a time (time intensive)
4) repeat

### DIY ArrayList implementation
```java
public class DIYArrayList {
	private static int DEFAULT_SIZE = 1;
	private static int GROWTH_FACTOR = 2;
	private int nextPosition;
	// for simplicity, we will store strings only
	private String[] values;

	public DIYArrayList() {
		nextPosition = 0;
		values = new String[DEFAULT_SIZE];
	}

	public DIYArrayList(int initialSize) {
		nextPosition = 0;
		values = new String[initialSize];
	}

	public String get(int idx) {
		return values[idx];
	}

	public boolean contains(String value) {
		// only loop over indeces that have values in them
		for (int i=0; i<nextPosition; i++) {
			if (s.equals(value)) {
			return true;
			}
		} 
		return false;
	}

	public int size() {
		return nextPosition;
	}

	// adding new value to ArrayList
	public void add(String toAdd) {
		if(nextPosition >= values.length) {
			growArray();
		}

		values[nextPosition] = toAdd;
		nextPosition++;
	}

	// make bigger array to make more space
	private void growArray() {
		String[] oldValues = values;
		values = new String[values.length * GROWTH_FACTOR];

		for (int i=0; i<oldValues.length; i++) {
			values[i] = oldValues[i];
		}
	}
}
```

*Static variables* belong to the class, much like static methods.

### ArrayList .add() method:
- if there are empty indeces, constant time
- if resizing and copying an array, takes more time

### ArrayList growth
- If we double with every growth, must copy elements at 1, 2, 4, 8, etc.
	- Total copies made is 1+2+4+8+...+N
	- Roughly 2N copies (using geometric series formula)
	- This is *Linear Time*
- If we add 100 with every growth, must copy elements at sizes 1, 101, 201, etc.
	- Total copies made is 1+101+102+...+N
	- Roughly (N^2) / 200 copies (using arithmetic series formula)
	- This is *Quadratic Time*

Q: What is *amortized constant time*?

- 2N copies to add N elements to arrays
- 2N/N = 2, which is a constant that doesn't depend on N

A: Constant time *on average* even if some additions require time (when copying)