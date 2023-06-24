# Css pseudo classes

## Pseudo-classes

Prefixed by a colon `:`, they are a different way to target elements that
already exist.

They have the same specificity as classes of 0,0,1,0.

[list of all pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

Example: 

```css
button:hover {
  color: blue;
}
```

### Dynamic and user action pseudo-classes

- `:focus`
- `:hover`
- `:active` element being clicked
- `:link` unvisited link
- `:visited` visited link

### Structural pseudo class

- `:root` represent top level of document, where global css rule aare apply.
- `:first-child` `:last-child`
- `:empty` match elements with no child
- `:nth-child()` flexible class with different uses, see example below:

```css
.myList:nth-child(5) {/* Selects 5th element with .myList */}

.myList:nth-child(3n) { /* Selects every 3rd element with .myList */}

.myList:nth-child(3n + 3) { /* Selects every 3rd element with class myList, beginning with the 3rd */}

.myList:nth-child(even) {/* Selects every even element with class myList */}
```
