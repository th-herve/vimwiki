# Java polymorphism

## Using superclass's methods

Simply call them by appending a `.`

```java
subClass.superClassMethods();
```

## Overriding superclass methods

Define a method with the same name in the subclass with `@Override` place above it.

```java
public Cat extends Animal {
    // code
    @Override
    public void speak() {
        System.out.println("meow");
    }
}
```
