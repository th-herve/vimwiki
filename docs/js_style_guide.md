# Javascript sytle guide

- [Airbnb sytle guide](https://github.com/airbnb/javascript) --> most popular
- [Google sytle guide](https://google.github.io/styleguide/jsguide.html#formatting-braces)
- [Javascript standart style](https://standardjs.com/rules.html)

## Basics rules

Most common rules.

### Indentation

Use 2 spaces

### Name

- variable: camelCase
- class and constructor: PascalCase
- Constants and global variables: UPPERCASE

### Quotes

Use single quotes for string unless escaping is necessary.

```javascript
let str = 'my string';
```

### Spacing

Use space after keywords `if for while` and 
around operators `= + -...`

```javascript
if (true) {
   // code 
}
```

### Function

Use named function expression instead of function declaration.
Give the variable a short name and the function a longer more
descriptive name.

```javascript
// bad
function addEntry() {
    //code
}

// good
const addEntry = function addNewEntryToArray() {
    // code
}
```
