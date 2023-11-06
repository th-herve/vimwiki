# Java list

Similar to array but have mutable and dynamic size.

## Declaration

Declare an `ArrayList` object with the type in angle bracket `< >`
A size can be specify in between bracket, if left empty, it default to 10

`!!` Can't declare a primitive as type. So no int, char...

```java
// we use Integer instead of int, create an list of 10 elements
List<Integer> myList = new ArrayList<Integer>();

// list of 12 elements
List<Integer> myList = new ArrayList<Integer>(12);
```

## Adding elements

Use `.add()`. It takes an optional index and the value to add.

```java
myList.add('foo');
myList.add(2, 'baz');
```

`!!` you can only add to a specific index if it already exists.

## Retrieving value

Use `.get()` with the index.

```java
myList.get(1);
```

## Removing

Use `.remove()` with the index or the first occurrence.

```java
myList.remove(1);
myList.remove('foo')
```
