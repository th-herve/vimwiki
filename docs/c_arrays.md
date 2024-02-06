# C arrays


```c
int num[] = {1, 2, 3, 4}; // the size is automatically set to the number of value initialized

int nbr[10] = {1, 2, 3, 4} // if a size is specified, and there is less value initialized, other elements are set to 0


char str = "boo";
// is a shorthand for:
char str[] = {'b', 'o', 'o', '\0'};
```

## 2d array

`type name[row][col]`

```c
int arr[10][10]; // declare a 2d array of int
int arr[][2] = { // with initialisation, the first size can be omitted
  {1, 2},
  {3, 4}
};
```

## Array of pointers

An alternative to the 2d array that allows to have different size for each row.

```c
char *weekEnd[] = {
  "saturday",
  "sunday"
};

printf("%s\n", weekEnd[0]);
```
