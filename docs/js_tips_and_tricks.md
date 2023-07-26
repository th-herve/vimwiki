# Javascript tips and tricks

## Count occurrence in a string or array using regex

Count occurrence of a character or expression...

```javascript
let string = 'How many vowel'
let count = (string.match(/[aeiouy]/g || []).length)
```
`.match()` return a array with the match.
However it return null if no match is found. That is why the `|| []` is necessary.
Otherwise, the `.length` throw an error.

