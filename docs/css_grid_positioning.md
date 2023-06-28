# Css grid positioning

## Terminology
 
- `tracks`:
     Row and columns of a grid. For a 3x3 grid, there is 3 `horizontal tracks`
     and 3 `vertical tracks`.
- `lines`:
     Every tracks has a `start` and `end` lines. It is used to `place`
     the grid items. A 3x3 grid has 1 to 4 horizontal lines and 1 to 4 vertical lines.
- `cells`:
     Space shared by a single row track and a single column track.
     By default, each item take one cell.

```markdown
l1 t1 l2  t2  l3    <-- col 
+-----+ +-----+ l1      row
¦ c1  ¦ ¦ c2  ¦ t1       |
¦     ¦ ¦     ¦          ↓
+-----+ +-----+ l2
+-----+ +-----+ 
¦ c3  ¦ ¦ c4  ¦ t2
¦     ¦ ¦     ¦
+-----+ +-----+ l3

c=cell l=line t=track
```
In the example, the cell 1 is placed in the track column 1 and track row 1, between the vertical
lines 1 and 2 and the horizontal lines 1 and 2.

## Positioning

To place an item, we use:

- `grid-column-start` and `grid-column-end` to specify the columns lines where the item start and end.
- `grid-row-start` and `grid-row-end` to specify the rows lines.
- `grid-column` or `grid-row`: is a shortend fort the start and end.

We can then moove items, or make them take more than one cell.

```css
div {
  display: grid;
  grid-template: 40px 40px / 40px 40px  ;
}

c1 {
  grid-column-start: 1;
  grid-column-end: 3;
  /* or */
  grid-column: 1 / 3;
}
```

```md
+-------------+
¦     c1      ¦
¦             ¦
+-------------+
+-----+ +-----+
¦ c2  ¦ ¦ c3  ¦
¦     ¦ ¦     ¦
+-----+ +-----+
```

### Grid area

The `grid-area` property is a shortend for `grid-row-start` / `grid-column-start` /
`grid-row-end` / `grid-column-end`

```css
item {
  grid-area: 1 / 1 / 3 / 6;
}
```

Another way to place items is to define a name for it with  `grid-area`, and
then in the container, use `grid-template-areas` to placed it like so:

```css
.container {
  display: grid;
  grid-template: 40px 40px / 40px 40px 
  grid-template-area: "first-item first-item" "second-item ." ;
}

.item1 {
  grid-area: first-item;
}
.item2 {
  grid-area: second-item;
}
```
An empty cell can be represented by a dot `.`
