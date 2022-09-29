# Lecture 2 - 31AUG22
### Before coding:
1. Understand problem
2. Work examples
3. Gather insights (generalize examples)

### Vocab:
- Java programs contain a single *class*, and are named *\<class name\>.java*
- Each program must have `public static void main` (*PSVM*) method
- If multiple files, only one file needs a *PSVM* file
- *Strongly typed* means the types of objects are explicitly cast 
- Primative types:
	- byte, short
	- int, long
	- float, double
	- boolean
	- char
- Only primative types can use `==` to check equality
- `+` can concatenate Strings
- *Reference types* use `new` keyword to create an instance, then run a `constructor` method
	- ex: `Scanner reader = new Scanner();`
- *Reference types* refer to an object is stored in memory, but doesn't store it itself
- *Arrays* hold a fixed number of values of a single type:
	- ex: `int[] numbers = new int[5]` creates an array of ints called `numbers` of length 5
	- *array* values are mutable
- *Strings* are just *arrays* of *characters*

### Loops
```java
// for
for (int i=0; i<numbers.length; i++) {
	System.out.println(numbers[i]);
}

// enhanced for 
// used to iterate through elements of an iterables
for (int number : numbers) {
	System.out.println(number);
}

// while
while (i < numbers.length) {
	System.out.println(number);
}
```

### Methods
- method *signatures* are the first line with names and arguments
	- ex: `public static void main(String[] args) {`
- *Dynamic methods* are called on an object and operate on the data stored in the class instance
	- ex: `x = "Hello"; System.out.println(x.length());`
- *Static methods* are called on the class itself
	- ex: `System.out.println(Math.sqrt(4,2));` uses the `sqrt` static method in `Math` class

### Iterables
- *Lists* can only hold reference type variables, so there are reference types for each primative types to let them be used in a list
	- ex: `int x = 5; Integer newX = x;`
- *HashSet* objects don't store duplicates, unlike *ArrayList* objects, which do