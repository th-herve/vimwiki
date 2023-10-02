# Java class basics

## General structure

```java
public class Car {
    public static void main(String[] args) {
        // code
      
    }
}
```

## Constructors

Help creating an object (instance of the class). Each time a instance is created
with `new`, the constructor is called.

The `this` keyword is use to refer to the object.

```java
// class
public class Cat {
    // fields
    String name;
    // constructor
    public Cat(name) {
        this.name = name;
    }
}

Car ferrari = new Cat("Felix");
```

## Instance fields

or `instance variable`, declare variable inside the class definition.

```java
class Cat {
    // instance fields
    String name;
    int numLives = 9;
    
    // constructor
    public cat() {
        
    }
}
```
