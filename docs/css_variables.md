# Css variables

Declare it with two dash `--`. Usually define in `:root`, and it `kebab-case`
Use it with the function `-var()`

```css
:root {
  --my-color: red;
}

div {
  color: var(--my-color);
}
```

## Fallback values

The `var()` function can take a second argument, that become the 
fallback value in case the variable failed.

Can be `nested` with another var().

```css
div {
  color: var(--my-color, blue);
  background-color: var(--my-color, var(--other-color, red));
}
```

## Scope

The scope of a variable include the selector where it is declared, and its 
descendants.

Setting them in `:root` make them accessible in the whole document.
