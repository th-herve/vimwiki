# Javascript loops

## Standart loop

for (initialiser; condition; final-expression) {
    // code to run
}

```javascript
for (let i = 0; i < 100; i++) {

}
```
## Loop over a collection

Javascript offer several ways to loop over a given collection, like an array.

### for...of loop

The `for...of` loop is a basic tool for looping over a collection.

```javascript
const names = ["Paul", "Henry", "Tanya"];

for (const name of names) {
    console.log(name);
}
```

### map()

Do something for each item in a collection and create a new collection
with `map()`.

```javascript
const upperNames = names.map(toUpper);
```

### filter()

Test each item in a collection, and create a new one with only the matching items
with `filter()`.

```javascript
const filteredNames = names.filter(name => name.startsWith("P"));
```

## While loop

```javascript
while (i < names.length) {
    // code to run
    
    i++;
}
```

## do...while loop

```javascript
let i = 0;

do {
    // code to run
    
    i++;
} while (i < names.length);
```
