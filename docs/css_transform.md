# Transform property

Change the appearance of elements without affecting the natural flow.
Commonly used for animation.

## Basics

`transform` take one or more css transform functions as its values.

## Function

### Perspective

The perspective function must be the first declare (the leftmost);

```css
.element { 
  transform: perspective() rotate3D();
}
```

### Rotate

```css
.element {
  transform: rotate(45deg);
  transform: rotate(-1rad);
  transform: rotate(0.3turn);
  
  transform: rotateX();
  transform: rotateY();
  transform: rotateZ();
  transform: rotate3D();
}
```

### Scale

Grow or shrink an element on one or two axis.

```css
.element {
  transform: scaleX(0.25);
  transform: scaleY(1.25);
  transform: scale(0.25, 1,25);
  
  transform: scaleZ();
  transform: scale3D();
}
```

### Skew

```css
.element {
  transform: skewX(45deg);
  transform: skewY(-0.5rad);
  transform: skew(45deg, -0.5rad);
}
```

### Translate

Move the element relative to itself.

```css
.element {
  transform: translateX(20px);
  transform: translateY(-33%);
  transform: translate(20px, -33%);
  
  transform: translateZ();
  transform: translate3D();
}
```

### Chaining transform

Separate transform function by a spaces.

```css
.element {
  transform: rotate(45deg) translate(20%);
}
```
