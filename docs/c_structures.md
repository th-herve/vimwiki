# Structures

```c
// define struc
struct car
{
  int year;
  char model[10];
  char plate[7];
  int miles;
  double engine_size;
  
};
// or to use only car when refering to it
typdef struct {
  int year;
  //...
} car;

// variable declaration
struct car mycar;
// or
car mycar;

// field accessing
mycar.year = 2011;
mycar.miles = 50000;
```

It can also be dynamically allocated.

```c
struct car *mycar = malloc(sizeof(struct car));

// field accessing

(*mycar).year = 2011;
// or
mycar->year = 2011;

```
