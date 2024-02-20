# Structures

Collection of one or more variable of different type.

## Declaration

Use the `struct` keyword, 

```c
struct car {
  char brand[10];
  int year;
  int miles;
  double engine_size;
};
// or to use only car when declaring the object
typdef struct {
  int year;
  //...
} car;

```
## Declaring a variable of type struct

```c
// define a variable of type car
struct car mycar;
// or
car mycar;

// with assignation
car mycar = {"fiat", 2011, 79000, 100.3};
```
## Accessing values

```c
// field accessing
mycar.year = 2011;
mycar.miles = 50000;

mycar.year++;
```
## Pointer to struct

```c
car *carP = &mycar;

(*carP).year = 2012;
// or
carP->year = 2012;
```
Note that the `->` operator is at the top of the precedence hierarchy with `[]` and `()`.  
- So `++carP->year` increments the year, not the pointer. Equivalent to `++(carP->year)`.
- `*carP->brand` dereferences the pointer brand, accessing the first letter of the brand.
- `*carP->brand++` fetches the letter pointed, then increments the pointer.

> It's better to pass the reference of a structure to a function, rather than copying the whole object.

## Dynamic allocation

```c
struct car *mycar = malloc(sizeof(struct car));

// field accessing
(*mycar).year = 2011;
// or
mycar->year = 2011;
```
