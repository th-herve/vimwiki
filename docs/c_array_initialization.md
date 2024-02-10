# C array initialization

## Basics initialization

```c
int arr[3] = {1, 2, 3};
int arr[] = {1, 2, 3}; // same thing
```

## Initialization with all values to 0

```c
int arr[10] = {  };
int arr[10] = { 0 }; // same thing
```

## Initalization with all values to the same number

`!!` only if compiling with `gcc`.

```c
int array[10] = {[0 ... 9] = 5};
```
Or with using a macro:

```c
#define x1 2 // replace 2 with the value needed
#define x2 x1, x1 
#define x4 x2, x2 
#define x8 x4, x4 
#define x16 x8, x8 
#define x32 x16, x16 

int num[] = { x32, x8, x4, x1}; // 32+8+4+1= 45 value set to 2
```

%% ## Initalization with enum indices

```c
enum Fruit_t {
    APPLES,
    ORANGES,
    STRAWBERRIES = 8
};


static const int price_lookup[] = {
    [APPLES] = 6,
    [ORANGES] = 10,
    [STRAWBERRIES] = 55
};

```
