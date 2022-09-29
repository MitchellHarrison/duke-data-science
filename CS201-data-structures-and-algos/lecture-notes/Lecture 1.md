# Lecture 1 - 29AUG22
**Q**: What is computer science?

- cpus execute algos using data to do something
- algos, machines, math, applications of computing
- interdisciplinary

**C**: the study of the use of programs, executed on a machine, that uses algorithms and data structures to do something

**Q**: What CS makes possible

- interdisciplinary needs

**C**: The bredth of use cases for CS makes it a helpful path across most disciplines, leading to the large community we have now.

**Q**: Why CS?

- informs society

**C**: Citizens require a base level understanding of computation

**Q**: What are algos?

- design: math, logic, problem solving
- implement (*abstraction*): syntax, semantics, languages, programming 
- algos: specified in formal language that can be executed on a machine

**C**: *precise* sequence of *unambiguous* steps that compute an output given an input

**Q**: What is code?
**C**: program written in formal language executed on machines

**Q**: What are data structs?

- *array* v *list*: (fixed len vs dynamic, less vs more memory, etc.)

**C**: store data in different ways with algorithmic tradeoffs

**Q**: Why does efficiency matter?
**C**: large user bases, massive datasets, pushing tech limits

### read txt file (with ArrayList [slower])
```java
// TODO import ArrayList
import java.io.File;
import java.util.Scanner;
import java.util.ArrayList;

public class Main{
	public static void main(String[] args) throws FileNotFoundException {
		// read from text file
		Scanner reader = new Scanner(new File("data/file.txt"));
		int numWords = 0;
		List<String> uniqueWords = new ArrayList<>();
		
		// count total number of words
		while (reader.hasNext()) {
			String word = reader.next();
			if (!uniqueWords.contains(word)) {
				numwords++;
				uniqueWords.add(word);
			}
		}
	}
}
```

### read txt file (with HashSet [faster])
```java
// TODO import ArrayList
import java.io.File;
import java.util.Scanner;
import java.util.HashSet;
import java.util.Set;

public class Main{
	public static void main(String[] args) throws FileNotFoundException {
		// read from text file
		Scanner reader = new Scanner(new File("data/file.txt"));
		int numWords = 0;
		Set<String> uniqueWords = new HashSet<>();
		
		// count total number of words
		while (reader.hasNext()) {
			String word = reader.next();
			if (!uniqueWords.contains(word)) {
				numwords++;
				uniqueWords.add(word);
			}
		}
	}
}
```

### Course goals:
- design, dev, debug java progams for problem solving
- implement and use data structures and algorithms
	- evaluate time and memory space complexity of iteratively and recursively defined algos