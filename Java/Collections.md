# Sequence Types
## Arrays
- fixed size after creation
- accessed via position - `[]`

## Lists
There are two main ways of implementing a list:

#### LinkedList
```java
List<Integer> numbers = new LinkedList<>();
```
- Better when insertions or removals are frequent
- Access pattern is usually one of iterating over the entire sequence
- Creation of these lists is much faster than ArrayLists

#### ArrayList
```java
List<Integer> numbers = new ArrayList<>();
```
- Better when access pattern is unpredictable
- Better when we don't often need to do insertions or removals


#### Methods
`.add` - add an element to list
`.size()` - get length of list
`.remove(4)` - remove element at position 4

`Collections.sort(list)` - sort list
`Collections.shuffle(list)` - shuffle llist

## Stack + Queue
Stack - LIFO
Queue - FIFO

These are both implemented using a **deque** (double ended queue).
Implemented using either `ArrayDeque` or `LinkedList`

```java
Deque<String> stack = new ArrayDeque<>();
stack.push("Alice");
stack.push("Bob");
stack.push("Charlie");
while (!stack.isEmpty()) {
	System.out.println(stack.pop());
}
```

```java
Queue<String> queue = new ArrayDeque<>();
queue.add("Alice");
queue.add("Bob");queue.add("Charlie");
while (!queue.isEmpty()) {
	System.out.println(queue.remove());
}
```


# Associative Collections
- These are UNORDERED collections. 
- Instead these are accessed using **key value** pairs

## Maps
Three main types:
- `HashMap` - fast but keys are not ordered
- `LinkedHashMap` - bit less efficient, but preserves order of key-value insertion
- `TreeMap` - least efficient, keeps keys sorted into their 'natural order' or according to the provided comparator

#### HashMap
- Implemented as an array of n buckets - linked lists of `Entry` objects
- Each `Entry` object holds key, value and a `hashcode` of the key
- `n` is a power of two, initially 16; when 75% of the buckets are non-null, array size is doubled and entries are redistributed.
- Initially all buckets are initialised to null
- The `hashcode` is derived from the key and the index
- Multiple key-value pairs can be stored in the same bucket, and each bucket is searched once indexed to find the correct key-value pair

#### TreeMap
- Implemented using a self-balancing binary search tree
- Goal is to optimise search
- Tree re-balances itself after insertions
- Elements that come before the parent go on the left, and if they come after the parent they go on the right

#### Creation
```java
Map<String, Integer> map1 = new HashMap<>();

Map<String, Integer> map2 = new LinkedHashMap<>();

Map<String, Integer> map3 = new TreeMap<>();
```
**Key should be an immutable type**
First type is key, second type is value.

#### Methods
`.put(key, value)` - put a key-value pair into the map
`.size()` - size of map
`.isEmpty()`
`.containsKey(key)` - check to see if it contains certian key
`.containsValue(value)` - check 
`.get(key)` - returns value for a key or if key does not exist RETURNS NULL (need to handle this)
`.getOrDefault(key, default)` - returns value for a key or if key does not exist returns the specified default value
`.remove(key)` - removes give key-value pair for a key
`.clear()` - removes everything from a map

For each loop to iterate over keyset of a map.
```java
for (String key: map.keySet()) {
	System.out.println(key);
}
```

## Set
- Like a map but does not store values, only keys
- Cannot contain duplicates
- Implemented via the `Set` interface
- Use `.add()` rather than `.put()` to add values
- Also has `HashSet`, `LinkedHashSet`, `TreeSet` implementations



