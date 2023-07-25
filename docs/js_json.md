# Javascript Json

## Receiving json

When receiving json data from a web server, it´s a string.
Convert it to a javascript object with `JSON.parse()`

```javascript
const jsonFromWeb = '{"name": "John", "age": 30}'
const obj = JSON.parse(jsonFromWeb);
obj.name
obj["age"]
```
> Note: Also work with array

## Sending json

When sending data to a web server, the data has to be a string.
Convert a javascript object to a string with `JSON.stringify()`

```javascript
const obj = '{"name": "John", "age": 30}'
const str = JSON.stringify(obj);
// send it 
```
> Note: Also work with array
