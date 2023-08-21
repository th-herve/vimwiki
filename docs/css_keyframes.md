# Css keyframes

## Animation properties

The keyframes work with the following animations properties:

- animation-duration
- animation-name: identifier used when declaring the keyframe
- animation-iteration-count: can be set to `infinite`
- animation-direction: set it to `alternate` to have the animation alternate direction on completion

```css
.element {
  animation-duration: 2s;
  animation-name: change-color;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

## Keyframes

Define state at given animation time.
The keyword from/to are aliases for 0%/100%.

```css
@keyframes change-color {
  from {
    background-color: red;
  }
  
  50% {
    background-color: blue;
  }

  to {
    background-color: green;
  }
}
```
