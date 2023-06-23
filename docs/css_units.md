# Css units

Use relative units (em or rem) for font-size and px for the rest (opinionated).

## Relative units

The most used are `em` and `rem`. Usually you should prefer `rem`.

### rem

`rem` value is based on the `root element's font-size`. It usually refers to the `html` element.

For example, if the html element has a font-size of 1px, and has a div child with the
width set as 2em. It's width would be 2 * 1px: 2px.

### em

`em` value is based on the `parent element's font-size`.

For example, if an element has a font-size of 1px, and has a div child with the
width set as 2em. It's width would be 2 * 1px: 2px.


## Absolute units

Just use `px` if in need of absolute units for web.

## Viewport units

`vh` and `vw` relate to the size of the viewport. 

- 1vw = 1% of the viewport width
- 1vh = 1% of the viewport height

- vmin = percentage of the viewport width or height, whichever is smaller 
- vmax = percentage of the viewport width or height, whichever is larger

It can be used with `calc()` to have a size that change with the viewport at 
a more moderate speed:

```css
h1 {
  font-size: calc(16px + 1vw);
}

h2 {
  font-size: calc(1.2em + 3vw);
}
```
