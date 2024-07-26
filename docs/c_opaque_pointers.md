# C opaque pointers

In C an opaque pointers allow to use a struct, while hidding its implementation and field.

## Usage

```c 
// car.h
typdef struct myCar Car;

Car *createCar();
void addWheels(Car *c);
```

```c
// car.c
typdef struct myCar {
    int nbrWheels;
    char *color;
} Car;
```

A file that include 'car.h', will be able to create and use the `Car` struct, without accessing the `color` and `nbrWheels` attributes.

`!!` the user's of Car can only use pointer to it, and cannot dereference it.
