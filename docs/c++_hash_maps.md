# C++ hash maps

A `hash map` or `map` is a data structure that stores a collection of elements with a
`key-value` pair. Like a `dictionary` in other language.

## Create a map

There are two types of maps

- `unordered_map`
- `map`

Include the `map` library and create a map with:

```cpp
std::unordered_map<key_type, value_map> [name];
```

```cpp
#include <unordered_map>
#include <map>

std::unordered_map<std::string, int> breiz_dep;
```
You can initialize a hash at creation with an initializer list.

```cpp
std::unordered_map<std::string, int> breiz_dep = {
        {"Morbihan", 56},
        {"Finister", 29},
        {"Cote d'Armor", 22}
    };
```
>`!!` the key-value are separated by a comma `,` not a colon `:`

## Hash maps methods

### Add elements

Use `.insert()` or the `[]` operator. The last is also used to access elements,
but will create it if not existing.

```cpp
breiz_dep.insert({"Cote d'Armor", 22});
breiz_dep["Ille et Vilaine"] = 35;
```
### Remove elements

Use `.erase()` with the `key`.

```cpp
breiz_dep.erase("Pays de la Loire");
```

### Check for an element

Use `.count()` to check if a `key` is in the map.

```cpp
breiz_dep.count("Pays de la Loire");
```
### Access an elements

Use the `[]` operator or `.at()`

`.at()` should be preferred because it does not insert the element if not present.

```cpp
std::cout << breiz_dep["Morbihan"];

std::cout << breiz_dep.at("Morbihan");
```

### Size of a hash map

Use `.size()` to get the size of a map.
Or `.empty()` to know if it's empty or not(return 1 or 0).

```cpp
breiz_dep.size();
breiz_dep.empty();
```

### Iterating through a hash map

Use a [for-each loop](c++_loops#for-each).
The counter variable is the hash map itslef, which is an object of type `std::pair`.
It has two member variables `.first` which is the `key` variable. And `.second` 
which is the `value` variable. Both can be used inside the loop.

```cpp
for(auto mp: breiz_dep) {
    std::cout << "key: " << mp.first << " value: " << mp.second;
}
```

## Order vs unordered map

`unordered_map` stores elements in no particular order.
Inserting, deleting and searching is faster in a `unordered_map`.  

`map` store elements in order.  

>Note: only use `map` when elements need to be sorted.
