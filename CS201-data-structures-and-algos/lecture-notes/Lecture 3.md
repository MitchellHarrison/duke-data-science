# Lecture 3 - 05SEP22
## Catalyst Duke Group
- Pre-pro/social tech group
- Rush starts thursday/sunday

## Java style
- one word names are `lowercase`
- multi-word is `camelCase`
- class names are `CapitalCase`
- Comments: `//`, multi-line: `/* */`
- Java looks like a multi-line comment with an extra star at the first slash `/** */` and will format documentation for you.

## Java notes
- *sets* are unordered, *lists* are ordered
- *sets* cannot be indexed like `set[1]` because they aren't ordered
- *lists* are mutable, *arrays* are not
- *ArrayList*, *HashSet*, etc. cannot store primative types, hence the reference type wrappers. `Integer`, `Character`, etc.
- *arrays* can hold primative types

## Object-Oriented Programming
Q: What is an "object-oriented" language?
A: Programs are organized by the specification and use of objects.

Q: What is an object?
A: some internal data items and operations that can be performed on that data

Q: What are the two components of every object?
A: Data, methods

**Defining classes:**
```java
Public Class Point {
	// start with data inside this type
	public double x;
	public double y;

	// constructor called when instanciating and has the same name as class
	public Point(double x, double y) {
		// "this" is the instance of a class on which this method is called
		this.x = x;
		this.y = y;
	}
}
```

Q: What are the two reasons to call a method?
A: For the side effect; For the return value

Q: What is a side effect?
A: What a method does to an object. `HashSet.add();`

Q: What is the `==` operator used for?
A: Checking for equality of *primative types*

Q: How do we check quality for reference types?
A: Using the `.equals()` method.

Q: How many data types can a *HashSet* or *ArrayList* store?
A: One.

Q: What does `==` check for with reference types?
A: Checking to see if both objects are the same thing in memory (does not compare values).

### Overriding default .equals method
```java
// this denotes the method as an override of one inerited from the Object class
@Override
public boolean equals(Object a) {
	// new logic goes here
}
```

Q: What class do all other Java classes inherit from?
A: The `Object` class.

### Creating array of custom objects
```java
ArrayList<Point> pointList = new ArrayList<>();

// use *new* keyword for every new point in ArrayList (10 times)
for (int i=0; i<10; i++) {
	pointList.add(new Point(0,1));
}

Point p = new Point(0,0);
System.out.println(pointList.contains(p));
```

### Note about .contains()
The `.contains()` method uses whatever `.equals()` method is defined for the objects inside of an iterable.