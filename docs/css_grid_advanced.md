# Css grid advanced

## Repeat

`repeat()` simplify the declaration of rows and columns of a grid.

```css
div {
  display: grid;
  grid-template-rows: 150px 150px;
  /* or */
  grid-template-rows: repeat(2, 150px);
}
```

## Fractional units

The `fr` or fractional units distribute the remaining space in the grid.
It is useful to make the grid items grow and shrink dynamically.

In a 400px wide container, with 4 columns given 1fr, each item would be
assign one fraction of 400px or 100px.

Some track can be bigger by setting a bigger fr value.
```css
div {
  grid-template-columns: repeat(2, 2fr) repeat(3, 1fr);
}
```

## Minimum and maximum track size: min() and max()

By default, the browser apply a `min-content` value on the grid item that
stop them from shrinking too much.

But it is better to not rely on this and use [min() and max()](css_functions#min)

```css
div {
  grid-template-rows: reapeat(2, min(200px, 50%));
  grid-template-column: reapeat(2, max(120px, 15%));
}
```
## Dynamic minimum and maximum

Min() and max() can be replaced by the `minmax()` function.
It only apply to grid and on these properties:

- `grid-template-columns`
- `grid-template-rows`
- `grid-auto-columns`
- `grid-auto-rows`

It take two arguments that set the minimum size the grid track can be
and the maximum.

```css
div {
  grid-template-rows: reapeat(2, 1fr));
  grid-template-column: reapeat(2, minmax(150px, 200px)));
}
```
## Clamp

The [clamp()](css_functions#clamp) function can also be applied:

```css
div {
  grid-template-rows: reapeat(2, 1fr));
  grid-template-column: reapeat(2, clamp(150px, 20%,200px)));
}
```

## Auto-fit and auto-fill

`auto-fit` and `auto-fill` are part of the `repeat()` function.
Allows to have a flexible number of columns based on the size of the grid
by calculating the first value of the `repeat` function.

It returns 'the largest possible positive integer' without the grid items
overflowing their container.

With a static value, it set the number of row/column automatically `repeat(auto-fit, 150px)`.
With a dynamic value, mostly `minmax()` it create a `wrap` `repeat(auto-fit, minmax(150px, 1fr))`

```css
div {
  display: grid;
  width: 1000px;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
K
```

Most of the time, `auto-fit` and `auto-fill` behave the same.
The difference appear when there is no enough item to all fit in the first
row at once. In this case, `auto-fit` will `stretch` its items, `auto-fill` won't.

```md
     container size
<----------------------->

auto-fit
+----------+ +----------+
¦          ¦ ¦          ¦
¦          ¦ ¦          ¦
+----------+ +----------+

auto-fill:
+-----+ +-----+
¦     ¦ ¦     ¦
¦     ¦ ¦     ¦
+-----+ +-----+
```
>`!!` It only apply for the first row. 
> If there is enough item to go into a new row, they will not stretch.
