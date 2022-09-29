# Lecture 6 - 14SEP22
## Duke Applied ML
Runs *Phoenix Project* to connect students to remote summer internships

Course-based and project-based training pipeline before joining.

[Website](https://daml.notion.site/Onboarding-aebb19f8c8104f50b37f9d569d8dd935https://daml.notion.site/Onboarding-aebb19f8c8104f50b37f9d569d8dd935)

## Notes
Q: What is a *Hash Table*?
A: Non-language-specific that uses a hash of key to determine where to store/look up values

Q: How to hash tables store k/v pairs?
A: Use hash function to get int from passed in key value, and same hash function to search for that key later

#### Finding valid index for key
This line gets a valid index in range of the length of the list 
`Math.abs(key.hashCode()) % list.size()`

When using `put`, if there's already a value at an index, it updates

`get` uses the same function to find the index and search there without looping

#### Collisions
Q: What are *collisions*?
A: When hash function % size returns the same value, trying to map a new key to an occupied position in the hash table.

Q: What is a *bucket* in a hash table context?
A: Each position of a hash table contains a list (or "bucket") of k/v pairs called

Q: Iterating through every bucket in a hash table to find the correct k/v pair is called \_\_
A: *chaining*

If multiple k/v pairs are in the same bucket, the `.equals()` method is called to see which key is the one we are searching for.

Q: What makes a `.hashCode()` implementation correct?
A: Any two objects that are `.equals()` should have the same `hashCode()`.

If you don't implement your own `.hashCode()` method, your class will inherit from `Object`, which uses the space in memory to find the hash. That's sub-optimal  since every object, even those that have the same parameters, will hash differently.

#### TODO (from slides) Sample `.hashCode()` method:
```java
@Override
public int hashCode() {
}
```

#### Hashing Efficiency
Things involved:
- Time to get hash
- Time to search over k,v pairs in a *bucket* using `.equals()`

HashMaps/HashSets are more effecient with more buckets

Q: What makes a `.hashCode()` implementation correct and efficient?
A: Same values return same `int`, different values always return different `int`

#### Simple Uniform Hashing Assumption (SUHA)
*N* pairs to *M* buckets

Q: What is SUHA?
A: Probablility that something is mapped to a given bucket is randomly spread across all buckets

This means that buckets should have *N/M* entries per bucket

#### Memory/Runtime tradeoff
N > M: too many pairs in too few buckets (inefficient runtime)
M > N: too many buckets (good runtime, too much memory)
M slightly larger than N: **sweet spot** (reasonable memory, constant runtime)



#### Load Factor, HashMap growth
Q: What is a *load factor*?
A: Maximum element/bucket ratio allowed

Q: What is Java's default *load factor*?
A: 0.75 (new hash table and copy when 75% full)

Whenever a hash table exceeds its load factor, Java doubles the size

Q: What is a *resizing operation*?
A: A function that increases the size of the hash table, recalculates the hashes, and refills the new hash table

