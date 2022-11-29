# Lecture 10 - 03OCT22
## Notes
Links in liked lists have data and a reference to the next link in the list (last points to null)

Adding and removing from front are O(1)

### Note on Linked List runtime
Looping with normal for loops is quadratic because it starts from the beginning of the list every time

Looping with an enhanced for loop is linear, as it does not start over from the beginning of the linked list every time.

## DIY Linked List
```java
public class ListNode {
	public String info;
	public ListNode next;

	public ListNode(String s) {
		info = s;	
	}

	public ListNode(String s, ListNode next) {
		info = s;
		this.next = next;
	}
}

public class LinkedList {
	ListNode first;
	ListNode last;
	int size;

	public LinkedList() {
		size = 0; // first and last will be null
	}

	public void add(String toAdd) {
		// edge case - list is empty, last is null
		if (last == null) {
			last = new ListNode(toAdd);
			first = last;
		} else {
			// common case - list not empty, last not null
			last.next = new ListNode(toAdd);
			last = last.next;
		}
		size++;
	}

	public String get(int idx) {
		if (idx < 0 || idx >= size) {
			throw new IndexOutOfBoundsException();
		}
		ListNode current = first;
		for (int i=0; i<idx; i++) {
			current = current.next;
		}
		return current.info;
	}

	public int size() {
		return size;
	}

	public boolean contains(String lookFor) {
		ListNode current = first;
		while(current != null) {
			if (current.info.equals(lookFor)) {
				return true;
			}
			current = current.next;
		}
		return false;
	}
}
```

## Creating/Traversing Linked Lists
The variable for the list itself is the reference to the first node

### Append one list to another using linked lists
```java
ListNode first = listA;
while (listA.next != null) {
	listA = listA.next;
}
listA.next = listB;
return first;
```
