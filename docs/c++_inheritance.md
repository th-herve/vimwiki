# C++ inheritance

`Inheritance` is the concept of defining a class from another class.
It make it simpler to implement new class by `reusing` code.
It establish hierarchical relationships between classes.

## Basic inheritance

Classes belonging in a inheritance relationship are separated into two groups:

- `Base class` or `parent class`: The class being inherited from.
- `Derived class` or `child class`: The class that inherits from the base class.

A derived class inherits attributes and methods from its base class.

Declare a derived class with `:`

[class] [ChildClass]`:` [access modifier] [ParentClass] {...};

```cpp
class Car: public Vehicle {
private:
    std::string color;
    ...
};
```
The class Car inherit the attribute and method of Vehicle, and create its own `color` attribute.

## Constructor inheritance

If you follow good practice, the attribute of a class should be `private`.
A derived class can still initialize its parent private attributes,
by using the parent's constructor in a [member initializer list](c++_constructors#Member-initialiser-lists)

```cpp
class Vehicle {
private:
    std::string brand;
    int wheels;
public:
    // constructor
    Vehicle (std::string new_brand, int new_wheels) 
        : brand(new_brand), wheels(new_wheels) {}
};

class Car {
private:
    std::string color;

public:
    // Car's constructor calls Vehicle's constructor, then implement its own constructor
    Car(std::string new_brand, int new_wheels, std::string new_color)
        : Vehicle(new_brand, new_wheels), color(new_color) {}
};

int main() {
    Car my_benz("Mercedes", 4, "blue");
}
```

## Multilevel inheritance

A class can inherit from a class that is also inheriting a class.
This create an `inheritance chain`.

```cpp
class A {    // A is the base class
public:
  int a;
 
  A() { std::cout << "Constructing A\n"; }
};
 
class B: public A {    // class B inherits from class A
public:
  int b;
 
  B() { std::cout << "Constructing B\n"; }
};
 
class C: public B {    // class C inherits from class B
public:
  int c;
 
  C() { std::cout << "Constructing C\n"; }
};
 
int main() {
  C example; 
 
  return 0;
}
```

The class at the top of the chain is always constructed first.
The order of construction goes from the parent to the child.

The above example gives us this output:

```cpp
Constructing A
Constructing B
Constructing C
```

## Type of inheritance

When declaring a derived class, they are three possibility of inheritance:

- `Public`: The access specifiers of the base class members stay the same in the derived class (most common).
- `Protected`: `Public` and `protected` members of the base class become protected in the derived class. 
- `Private`: All members of the base become `private` in the derived class.
