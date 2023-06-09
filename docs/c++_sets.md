# C++ sets

A `set` is a structure that stores multiple `unique` elements.
Its elements are not access by an index but by a `key value`.
Thus, a set can only contain the same value once.

In a set, the value of each elements acts as its own key.

## Create a set

There are two types of sets:

- `unordered_set`
- `set`

Include the `set` library and create a set with:

```cpp
std::unordered_set<type> [name];
```
```cpp
#include <unordered_set>
#include <set>

std::unordered_set<int> primes({2, 3, 5, 7});
```
>Note: if you try do add a duplicate value, only one will be kept.

## Sets methods

### Add elements

Use `insert()`

```cpp
primes.insert(2);
```
>Note: duplicate value won't be added.

### Remove elements

Use `.erase()`

```cpp
primes.erase(3);
```
>Return `1` if element successfully erased, `0` otherwise.

### Check for an element

Use `.count()` to search if an element is in the set.

```cpp
primes.count(4);
```

### Size of a set

Use `.size()` to get the size of a set.
Or `.empty()` to know if it's empty or not(return 1 or 0).

```cpp
primes.size();
primes.empty();
```

## Order vs unordered set

`unordered_set` stores elements in no particular order.
Inserting, deleting and searching is faster in a `unordered_set`.  
A `unordered_set` uses a `hash table` and provide `O(1)` complexity for basics operation

`set` store elements in order.  
A `set` uses `binary search tree` and provide `O(log n)` complexity for basics operation.

>Note: only use `set` when elements need to be sorted.
