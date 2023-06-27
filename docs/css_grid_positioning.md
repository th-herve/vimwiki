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

## Positioning


