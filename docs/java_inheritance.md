# Java inheritance


- superclass = class that another class inherits from.
- subclass = class that inherits

Create a superclass/subclass relationship with `extends`

```java
class Animal {
    // code
}

class Cat extends Animal {
    // code
}
```

## super() method

The `super()` method is called whenever an instance of a subclass is created.
It allows to pass argument to the superclass when creating an instance of a subclass.

```java
class Animal {
    int numLives;
    Animal(int numLives) {
        this.numLives = numLives;
    }
}

class Cat extends Animal {
    Cat() {
      super(9);
    } 
}
```
