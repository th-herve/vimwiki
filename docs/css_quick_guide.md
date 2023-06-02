# Css quick guide

/* Comment */
selector {
    property: value;
}

## selector


```css
* {}

.class-name {}

#id-name {}

h1 {}

selector:first-child {}

selector:last-child {}

/* Selects all direct child elements */
parent > child {}

/* Selects all sibling elements */
selector ~ sibling {}

/* Selects all adjacent sibling elements */
selector + sibling {}
```

## Common properties 

```css
/* Changes the font family */
font-family: Arial, sans-serif;

/* Changes the font size */
font-size: 16px;

/* Changes the font color */
color: #000000;

/* Changes the background color */
background-color: #FFFFFF;

/* Changes the padding */
padding: 10px;

/* Changes the margin */
margin: 10px;

/* Changes the border */
border: 1px solid #000000;

/* Changes the width */
width: 100px;

/* Changes the height */
height: 100px;

/* Changes the opacity */
opacity: 0.5;

/* Changes the text alignment */
text-align: center;

/* Changes the display */
display: block;

/* Changes the position */
position: relative;

/* Changes the z-index */
z-index: 1;

/* Changes the overflow */
overflow: hidden;

/* Changes the cursor */
cursor: pointer;

/* Changes the text decoration */
text-decoration: underline;

/* Changes the text transform */
text-transform: uppercase;

/* Changes the box shadow */
box-shadow: 2px 2px 2px #000000;

/* Changes the border radius */
border-radius: 10px;

/* Changes the transition */
transition: all 0.3s ease;

/* Changes the animation */
animation: name 1s infinite;

/* Media queries */
/* Changes the style based on screen width */
@media only screen and (max-width: 768px) {
    selector {
        property: value;
    }
}

```
