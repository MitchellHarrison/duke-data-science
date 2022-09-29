# Lecture 5 - 12SEP22
## Guest speaker notes (Dtech)
- Diverse leadership in tech
- Women only?

## Notes
- *arrays* can store primative or reference types
- *collections* can only store reference types
- `String[0]` tells java to infer the correct length of the array when converting an array from another iterable or vice-versa
- ***arrays do not have a `.contains()` method***

### Sets
- Store *unique* elements
- Has `.add()`, `.contains()`, `.remove()` methods among others
- Loop over a set (won't work with traditional for loop):
```java
for (String s : mySet) {}
```
- Convert between lists and sets (works in both directions):
```java
List<String> myList = new ArrayList<>();
myList.addAll(mySet);
```
- `.add()`, `.remove()`, `.size()`, and `.contains()` all have *constant time* performance with Sets
- *TreeSets* are nearly as efficient as *HashSets*, but *TreeSets* keep values ordered (but not in the order they are added)

Q: How to TreeSets order values?
	- alphabetical, numeric order, etc.
A: By sorting them


- In data structures/algos, *correctness* means getting the right output for a given input, regardless of optimization
- Get correctness first, then optimize


### Maps
- key/value pairs like *dicts*
- *maps* contain `.put(k,v)`, `.get(k)`, and `.containsKey(k)` methods among other
- *HashMap* `.put(k,v)`, `.get(k)`, and `.containsKey(k)` are constant time
- *TreeMaps* are nearly as effecient as *HashMaps*, but keys sorted
- **Check before you get**
```java
int val = myMap.get("hi"); // if map doesn't have "hi" key, crash will happen

// fix that problem
if (myMap.containsKey("hi")) {
	int val = myMap.get("hi")
}
```
- `.putIfAbsent(k,v)` method puts a default value `v` into a key if there isn't one for that key already
- If the values in a *HashMap* are other collections, you need to call `new` again to carve out memory for the new collections.
- If values in a *HashMap* are single values, the `.get()` method returns a copy of that value, but if it is a collection, `.get()` return a *reference* to that object in memory to avoid copying long collections (inefficient)
- Keys in *Maps* are unique