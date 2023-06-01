# C++ Polymorphism

Polymorphism applies to `class methods` in an inheritance relationship.

It allows a `derived class` to override methods inherited from its base.

```cpp
class Vehicle {
public:
    void description() {
        std::cout << "It's a vehicle";
    }
};

Class Car: public Vehicle {
public:
    // Car override the implementation of the description method
    void description() {
        std::cout << "It's a car";
    }
};
