# Css transition

The transition property is a shorthand for:

- transition-property: what css property will be transitioned
- transition-duration
- transition-timing-function: speed of the transition over its duration
- transition-delay: delay before transition start

[easing function cheat sheet](https://easings.net/)

```css
button {
  [transition property](transition-property.md): background-color;
  transition-duration: 1s;
  transition-timing-function: ease-out;
  transition-delay: 0.25s;
}

or

button {
  transition: background-color 1s ease-out 0.25s;
}

button:hover {
  background-color: black;
}
```

## Multiple transition

```css
button {
  transition:
    width 2s,
    height 2s,
    background-color 2s,
    rotate 2s;
}

button:hover {
  width: 200px;
  height: 200px;
  rotate: 180deg;
}
```
