# Javascript arrays methods

If you want to apply those methods on a node element (obtain with .querySelectorAll for example),
you need to first convert it to an array:

[List of methods](https://javascript.info/array-methods)

```js
const array = Array.from(document.querySelectorAll("div"));

// or 

const array = [...document.querySelectorAll("div")];
```

## array.filter()

Return a sub array that meet the filter requirement (return true)

```js
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

```js
const result = array.map(item => `${item.name} ${item.lastName}`);
```

## array.sort()

Return a reference to the given array, now sorted.

The sorting function must be specify. 

It work by returning 1 or -1 meaning moving a to up or down.

```js
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

```js
const result = array.reduce((accumulator, item) => {
    return accumulator + item.number;
},0);

```
>`!!` take note of the `0` at the end, it ensure that the function does not return undefined.

## array.some()

Check if at least one item in the array is true. 

Return `true` or `false`.

```js
// return true if one of the item is superior to 20
const result = array.some(item => {
    return item > 20;
});
```
>Note: the `return` keyword can be omitted

## array.every()

Check if all item in the array are true. 

Return `true` or `false`.

```js
// return true if all the items are superior to 20
const result = array.every(item => {
    return item > 20;
});
```
>Note: the `return` keyword can be omitted

## array.find()

```js
const result = array.find(item => array.name === "myName");
```

## array.findIndex()

```js
const index = array.findIndex(item => item.id === 321);
```
