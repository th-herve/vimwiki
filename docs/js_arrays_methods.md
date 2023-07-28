# Javascript arrays methods

If you want to apply those methods on a node element (obtain with .querySelectorAll for example),
you need to first convert it to an array:

[List of methods](https://javascript.info/array-methods)

```javascript
const array = Array.from(document.querySelectorAll("div"));

// or 

const array = [...document.querySelectorAll("div")];
```

## array.filter()

Return a sub array that meet the filter requirement (return true)

```javascript
const result = array.filter(item => {
        if (item.number > 100) {
            return true;
        }
});

// or 

const result = array.filter(item => item.number > 100); 
```

## array.map()

Map return an array with the `same` number of item than the one given.

```javascript
const result = array.map(item => `${item.name} ${item.lastName}`);
```

## array.sort()

Return a reference to the given array, now sorted.

The sorting function must be specify. 

It work by returning 1 or -1 meaning moving a to up or down.

```javascript
const result = array.sort(function(a, b) {
    if (a.age > b.age) {
        return 1;
    }
    else {
        return -1;
    }
});

// or

const result = array.sort((a, b) => a.age > b.age ? 1 : -1);
```
>Note: use `toSorted()` to return a new array.

## array.reduce()

The `reduce()` method execute a `reducer callback function` on each
element, and pass the return value from the calculation of
the last element.

The first callback does not have a return value. An initial
value can be supplied. Otherwise array[0] is used, and iteration start
at index 1.

The result is a `single value`.

Use cases: sum up array, finding min/max, flattening multi dimensional array,
grouping element, counting occurrence...


```javascript
const array = [1, 2, 3 , 4];

const result = array.reduce((accumulator, item) => {
    return accumulator + item;
}, 0); // 0 act as the first return value

// result = 10
```
> Note: the `0` provided as default value is useful if we had an empty array. Without it, it would throw an error. Wiht it, it return 0.

## array.some()

Check if at least one item in the array is true. 

Return `true` or `false`.

```javascript
// return true if one of the item is superior to 20
const result = array.some(item => {
    return item > 20;
});
```
>Note: the `return` keyword can be omitted

## array.every()

Check if all item in the array are true. 

Return `true` or `false`.

```javascript
// return true if all the items are superior to 20
const result = array.every(item => {
    return item > 20;
});
```
>Note: the `return` keyword can be omitted

## array.find()

```javascript
const result = array.find(item => array.name === "myName");
```

## array.findIndex()

```javascript
const index = array.findIndex(item => item.id === 321);
```
