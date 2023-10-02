# Java linked list

The built in `LinkedList` from java implement a doubly linked list.
It provides a more efficient way to manipulate data compared to `ArrayList`.

## Declaring

```java
LinkedList<String> myLinkedList = new LinkedList<String>();
```

## Adding

```java
myLinkedList.add('bar');
myLinkedList.add(2, 'foo');
```

## Retrieving

```java
myLinkedList.get(2);
```

## Removing

```java
// remove the index
myLinkedList.remove(2);

// remove first occurence
myLinkedList.remove('bar');
```
