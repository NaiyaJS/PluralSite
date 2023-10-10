# PluralSite
```markdown
# Java Collections - Lists and Maps

## Introduction
Java Lists and Maps are part of the Java Collections Framework, which provides a set of classes and interfaces to work with collections of objects.

### Collection Interface
The `Collection` interface is the root interface for all collections in Java. To be considered a collection, certain methods must be implemented, including `add()`, `remove()`, `size()`, `contains()`, and more. Collections can be divided into two subgroups: Lists and Sets.

### Set
A Set is a collection of unique values without an index. Sets are used to store a group of general Java objects.

### List
A List is an ordered group of values that are numerically indexed. It is also an interface, implementing methods of the `Collection` interface and providing its own methods, such as `add()`, `add() at index`, `set()`, `remove() at index`, `indexOf()`, `sublist()`, and `set()`.

You cannot instantiate a List directly, so you either build your own List or use Java's implemented non-abstract List classes like ArrayList, LinkedList, Vector, or Stack. To maintain flexibility, declare your List variable as a general List to change the type of the List throughout the code without altering the variable declaration.

### Adding elements to a List
```java
List<String> languages = new ArrayList<>();
languages.add("Java");
languages.add("Python");
languages.add("JavaScript");
languages.add("Go");
System.out.println(languages.size()); // Outputs 4
```

### Iterating through Elements in a List
Use a for-each loop to iterate and print out the elements in a List.
```java
for (String language : languages)
    System.out.println(language);
```
Output:
```
Java
Python
JavaScript
Go
```

### Index and Value
To retrieve an index of a specific value or a value at a specific index, you can use `indexOf()` or `get()`.
```java
System.out.println(languages.indexOf("Python"));
System.out.println(languages.get(2));
```

To remove elements from the list, you can use `remove()` either with an index or a value.
```java
languages.remove("Python");
languages.remove(2);
```

### Problems with Arrays
Arrays do not resize dynamically, which can be limiting.

### How List Solves the Problem
Lists can easily convert to arrays using the `toArray()` method.

#### Return an Array of Objects
```java
Object[] langsArray = languages.toArray();
```

#### Return an Array of Strings
```java
String[] langsArray = languages.toArray(new String[0]);
```

### Sublist
The `subList()` method returns a view of the list. Modifying the sublist will also change the original List.
```java
List<String> someLangs = languages.subList(0, 3);
someLangs.set(2, "Groovy"); // Changes the original List
```

## Map Interface
The `Map` interface represents an unordered collection of key-value pairs, indexed by keys.

### Keys
Keys can be any object and must be unique, while values can be repeated.

### Methods
The `Map` interface defines various methods, including `containsKey()`, `containsValue()`, `forEach()`, `keySet()`, `put()`, `size()`, and more.

To use a `Map`, you need to instantiate a non-abstract (non-interface) implementation, such as HashMap, TreeMap, or LinkedHashMap.

#### HashMap
```java
Map<String, Integer> coursesByLanguage = new HashMap<>();
```

Maps can hold keys and values of various types, such as `<Integer, String>`, `<String, MyProduct>`, or `<Integer, List<String>>`.

### Adding Values to a Map
You can use the `put()` method to add key-value pairs to a Map.
```java
Map<String, Integer> languagesCount = new HashMap<>();
languagesCount.put("HTML", 5);
languagesCount.put("CSS", 3);
languagesCount.put("JavaScript", 20);
System.out.println(languagesCount.size()); // Outputs 3
```

### Iterating through the Map
To iterate through a Map, you can use the `entrySet()` method, which returns a Set of key/value entries for iteration.
```java
for (Map.Entry<String, Integer> entry : languagesCount.entrySet()) {
    System.out.format("%d %s courses%n", entry.getValue(), entry.getKey());
}
```

A `Map.Entry` represents an individual key/value pair.

### Order Depends on the Type of Map
- `HashMap`: No order is guaranteed.
- `LinkedHashMap`: Insertion order is preserved.
- `TreeMap`: Elements are sorted by key.

# Java Collections with Uniqueness Sets
## HashSet

`HashSet` is an implementation of the `Set` interface that uses a hash table to store elements. It offers constant-time complexity for basic operations like adding, removing, and checking for the presence of elements. However, it does not maintain the order of elements. It ensures uniqueness by using the hash code of elements.

```java
Set<String> hashSet = new HashSet<>();
hashSet.add("Apple");
hashSet.add("Banana");
hashSet.add("Cherry");
hashSet.add("Apple"); // Duplicate, will not be added
```

## LinkedHashSet

`LinkedHashSet` is another implementation of the `Set` interface that maintains the order of elements in which they were inserted. It combines a hash table with a linked list, ensuring that the elements are both unique and ordered.

```java
Set<String> linkedHashSet = new LinkedHashSet<>();
linkedHashSet.add("Apple");
linkedHashSet.add("Banana");
linkedHashSet.add("Cherry");
linkedHashSet.add("Apple"); // Duplicate, will not be added
```

## TreeSet

`TreeSet` is a `SortedSet` implementation that stores elements in a sorted order based on their natural order or a custom comparator. Like other sets, it enforces uniqueness. Elements are automatically sorted when added to the set.

```java
Set<String> treeSet = new TreeSet<>();
treeSet.add("Banana");
treeSet.add("Cherry");
treeSet.add("Apple");
treeSet.add("Apple"); // Duplicate, will not be added
```


Java Collections Framework provides sets for managing collections of unique elements.
HashSet provides constant-time performance for basic operations and does not maintain order.
LinkedHashSet maintains the order of insertion while enforcing uniqueness.
TreeSet maintains elements in sorted order, either naturally or using a custom comparator.
Choose the appropriate set implementation based on your specific requirements for
uniqueness and ordering when working with collections in Java.
