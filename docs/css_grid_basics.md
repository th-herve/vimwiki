# Css grid basics

Create a grid with `display: grid;`. The container become the grid and all
its `direct` child become the grid items.

```css
div {
  display: grid;
}
```

## Defining rows and columns

Define them with the properties `grid-template-rows` and
`grid-template-columns`.

Or define it both with the shorthand `grid-template`,
separate the rows (first) and the columns with a slash `/`.

```css
div {
  display: grid;
  grid-template-rows: 50px 50px;
  grid-template-columns: 50px 50px 50px;
  
  /* or */
  grid-template: 50px 50px / 50px 50px 50px;
} 
```
This gives us a grid with two row of 50px and three columns of 50px.
If we had three item in the div container, it would gives us:

```markdown
+-----+  +-----+  +-----+
¦  1  ¦  ¦  2  ¦  ¦  3  ¦
¦     ¦  ¦     ¦  ¦     ¦
+-----+  +-----+  +-----+
+-----+ 
¦  4  ¦  
¦     ¦  
+-----+  
```

You can also use the function [repeat()](css_grid_advanced.md) to specify the row and column.

## Explicit vs implicit grid

In the example above we have a grid of 2 row and 3 columns,
which gives a container that can hold 6 items.

Those 6 items will be placed `explicitly` by our grid.
But if we add more items, those will be placed `implicitly` by the grid.

The size established in the `grid-template` do not carry over, but can be
define with `grid-auto-rows: 0px;`.

By default, they are placed in a new row, but this can be changed with
`grid-auto-flow: column;`. In this case, the size of implicit placed item
is defined with `grid-auto-columns: 0px;`.


## Gap

The gap, also known as gutter or alley, is defined with
`column-gap: 0px` and `row-gap: 0px;`
