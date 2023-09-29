# Java class basics

## General structure

```java
public class Car {
    public static void main(String[] args) {
        // code
      
    }
}
```

## Access modifiers

Four types:

| modifier    | class | package | child class | global |
|-------------|-------|---------|-------------|--------|
| public      | ✓     | ✓       | ✓           | ✓      |
| protected   | ✓     | ✓       | ✓           |        |
| no modifier | ✓     | ✓       |             |        |
| private     | ✓     |         |             |        |


## Constructors

Help creating an object (instance of the class). Each time a instance is created
with `new`, the constructor is called.

```java
// class
public class Car {
    // constructor
    public Car() {
        // code
    }
}

Car ferrari = new Car();
```
