# C++ access specifiers

Control access and determine the scope of class members.

Three main type:

- `private`: best for attributes
- `public`: best for methods
- `protected`: like private but allows inherited classes to access those members

Declare with `private:` or `public:`

```cpp
class Sport {
private:
    int number = 1;
public:
    std::string running;
};
```

## Private keyword

By default, class members are `private`. They cannot be directly access from outside the class.

>Note: declare class attributes as private whenever possible.

## Public keyword

`public` members are accessible anywhere in the program.

It is best used for methods. Provide ways for the program to interact 
with an instance of the class.

## Encapsulation

`Encapsulation` in OOP programming means hiding details about an object's implementation.

In C++ this translate by declaring a class members/attributes as `private`.
So they cannot be accessed from outside the class.

However, if the program may need to interact with those values, 
it can still do so with `accessor functions` and `mutator functions` (getter and setter).

## Accessor functions

An accessor functions (or `getter`) is a `public` function that `return`
the value of a `private` member.

```cpp
class Clock {
private:
    int time = 1200;
    
public:
    // getter for time
    int getTime() {
        return time;
    }
};
```

>Note: Accessor functions should always have a return type that matches the type of the member it is accessing.

## Mutator function

A mutator function (or `setter`) is a `public` function that
`sets` the value of a `private` member.

```cpp
class Clock {
private:
    int time = 1200;
    
public:
    // setter for time
    void setTime(int new_time) {
        time = new_time;
    }
};
```
>Note: They usually have a `void` return type and one parameter of the same type as the attribute.
