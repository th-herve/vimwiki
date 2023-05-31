# C++ classes and objects basics

## Classes

Use the `class` keyword to create one, end its definition with a semicolon `;`

```cpp
class Dog {
    // class elements
};
```
> ` ` Don't forget the semicolon at the end 

The element of a class are called `class members`, there are two types:

- `Attributes`: contain information about an object of the class.
- `Methods`: function that belong to the class.

```cpp
class Dog {
public:
    std::string name;
    int age;
    
    void bark() {
        std::cout << name << "is barking\n";
    }
};
```
Methods can be defined outside of the class (for example in their own separate file).
In that case, it need to be specified with `ClassName::`

```cpp
// outside of the Dog class definition
void Dog::bark() {
    std::cout << name << "is barking\n";
}
```

## Objects

Create an instance of a class or `object` 

```cpp
Dog mydog;
```

Use the `.` to access and modify its attributes or call its methods

```cpp
mydog.name = "Snoopy"

mydog.bark();
```
