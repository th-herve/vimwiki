# Css box model

On a website, everything is a box. And each box can contain boxes.

Add a border to see these boxes.

```css
* {
  border: 2px solid red;    
}
```

There are several ways to manipulate the size of these boxes.

- `padding`: increases the space between the border of a box and its content.
- `margin`: increases the space between the borders of a box and the adjacent boxex.
- `border`: add space between the margin and the padding.

## Block vs Inline

- `Block` elements appear on top of each other, each new element on a new line.
- `Inline` elements do not start on a new line. They appear one after the other.

> Padding and margin behave differently in block and inline.
> Usually you don't put those attributes on an inline element.

- `Inline-block` elements behave like inline elements but with block-style padding and margin.

## Div vs Span

Div and span are not associated with a particular type of content (as oppose as link, paragraph...)
They are just generic boxes that can contain anything.

- `Div` are block element by default.
- `Span` are inline element by default.
