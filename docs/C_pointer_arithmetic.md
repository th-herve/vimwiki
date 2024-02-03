## C pointer arithmetic example

### *p++

Dereferences the value of p, then increments it

```c
int a[] = {1, 2, 3, 4};
int *p = a

int x = *p++; // x = 1, p then point to 2
```
> `*--p` dereferences then increments

### *++p

Increments the pointer then dereferences it

```c
int a[] = {1, 2, 3, 4};
int *p = a

int x = *++p; // x = 2, p point to 2
```
> `*--p` decrements then dereferences

### (*++p)[i]

In the context of pointers to pointers, like `argv[]`.  

1. `++p` increment the pointer
2. `*++p` dereferences the pointer, accessing the `pointer` it points to
3. `(*++p)[i]` access the ith element of the array

```c
// by calling the program with: ./program -n hello
char c = (*++argv)[0] // move the pointer to the second command line argument '-n', and accesses its first char '-'
```
> Equivalent to `**++p`

### *++p[i]

In the context of pointers to pointers, like `argv[]`.  

1. `p[i]` get the ith pointer of the pointers array (`[]` is evaluated before `*++`)
3. `++p[i]` increments the ith pointer
4. `*++p[i]` dereferences the ith element of the array

```c
// by calling the program with: ./program -n hello
char c = *++argv[1] // access the argv[1] command line argument '-n' as a pointer, increment the pointer (now points at 'n', because first it was on '-'), access the value 'n'
```
