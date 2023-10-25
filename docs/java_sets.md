# Java sets

A `set` stores an `unordered` collection of `unique` values.

There is three implementations:

- `HashSet`
- `TreeSet`
- `LinkedHashSet`

## Comparison

|                                  | HashSet | TreeSet                   | LinkedHashSet |
|----------------------------------|---------|---------------------------|---------------|
| Elements order                   | random  | numerical or alpahbetical | order added   |
| can store null value             | Yes     | No                        | Yes           |
| add, remove, contains complexity | O(1)    | O(log n)                  | O(1)          |

## Creating a Set

Specify the data type of the elements and the type of set.
It can only contain `reference type` values.

```java
// import the desired set type
import Java.util.Set;
import Java.util.HashSet;
import Java.util.TreeSet;
import Java.util.LinkedHashSet;

// Create a string HashSet
Set<String> colors = new HashSet<String>();

// Create an integer Tree set
TreeSet<Integer> myNumbers = new TreeSet<Integer>();
```

## Methods

### Adding

```java
colors.add("red");
colors.add("red"); // duplicate is ignored
```
### Removing

```java
colors.remove("red");
```
### Checking a value

```java
colors.contains("red"); // true or false
```
### Size

```java
colors.size()
```
### Iteration

```java
for (String item : colors) {
  System.out.println(item);
}
```

## Set operations

The set classe provide methods to perform mathematical operations on two different sets.
Allowing to create or modify existing ones.

### Union

Use `.addAll()` to add all element of one set to another.

```java
Set<String> colors = new HashSet<String>();
Set<String> favColors = new HashSet<String>();

// add colors to them

// add the favColors to the colors set
colors.addAll(favColors);
```

### Intersection

Use `.retainAll()` to keep only in a set, the value that are common to another one.

```java
// only keep in colors, the ones that are also in favColors
colors.retainAll(favColors);
```

### Complement

Use `.removeAll()` to remove from one set, the value that are also in another one.

```java
// remove from colors, the one present in favColors
colors.removeAll(favColors);
```
