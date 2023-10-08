# Java hashmap

Store collection of key-value pairs.

## Creation

We import the hashmap and declare it by specifying both the key and the value data type.

`!!` cannot use primitive

```java
import java.util.HashMap;
HashMap<String, Integer> myHashMap = newHashMap<>();
```

## Adding key-value pair

```java
myHashMap.put("foo", 1);
```

## Accessing

Use `.get()` with the key.

```java
myHashMap.get("foo");
```

## Removing a value

Use `.remove()` with the key;

```java
myHashMap.remove("foo");
```

## Removing all

```java
myHashMap.clear();
```

## Size

```java
myHashMap.size();
```

## Traversing

Use a `for-each` loops

```java
for(String key : myHashMap.keySet()) {
    // code
}
```

## Other methods

### containsKey()

```java
myHashMap.containsKey(key);
```
### replace()

```java
myHashMap.replace(key, value);
```

### keySet()

Create a Set with all the keys in the hashmap.

```java
myHashMap.keySet();
```

### values()

Return a `collection` with all the values (without their key).

```java
myHashMap.values();
```
