# Css functions

The most used functions are:

- `calc()`
- `min()`
- `max()`
- `clamp()`

[List of all the functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions)

## calc()

Calculate a value with two powerful use cases:

- Mixing units
- Ability to nest `calc(calc())`

```css
:root {
  --header: 3rem;
  --footer: 40px;
  --main: calc(100vh - calc(var(--header) + var(--footer)));
}
```

## min()

Return the smallest value of a given list.

```css
div {
 width: min(150px, 100%);
}
```
In the example, if 100% of the parent width is less than 150px, it will be set 
to the parent width.

## max()

Return the largest value of a given list.

Not as usefull as `min()`

```css
div {
 width: max(150px, 100%);
}
```
In the example, if 100% of the parent width is more than 150px, it will be set 
to the parent width.

## clamp()

It take three value, the smallest, the ideal and the largest.

```css
    h1 {
      font-size: clamp(320px, 80vw, 60rem);
    }
```
