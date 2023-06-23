# Css fonts

## Use default system's user font

```css
body {
  font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
}
```
## Use online font libraries

Use font library like

- [goolge font](https://fonts.google.com/)
- [font library](https://fontlibrary.org/)

Add the selected font in your website either with:

- The `<link>` to add to the `html`
- The `@import` to add to the `css`

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">

@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
```

Then you can use the font in the css as normal.

>Note: always add a fallback font as this rely on an api that can become obsolete or not work as expected.

## Use downloaded fonts

You can download a font and then import it with `@font-face` in the `css`.

```css
@font-face {
  font-family: my-font;
  src: url(../fonts/my-font.ttf);
}

h1 {
  font-family: my-font;
}
```
>May be more reliable than an api font but some format are not supported by browsers.
> [list of browsers supported font](https://www.w3schools.com/css/css3_fonts.asp)
> [list of font format](https://fileinfo.com/filetypes/font)

## Font related attribute

### letter-spacing

Changes the spacing between letter.

```css
h1 {
  letter-spacing: .5em;
}
```
### line-height

Adjust space between lines in wrapped text. Can increase readability.

```css
p {
  line-height: 1.5;
}
```

### text-transform

Change the case of the given text.

Possible values: capitalise, uppercase, lowercase...

```css
h1 {
  text-transform: capitalise;
}
```

### text-shadow

```css
/* offest-x | offest-y | blur-radius | color */
h1 {
  text-shadow: 1px 1px 2px black;
}

/* offest-x | offest-y | color */
h2 {
  text-shadow: 1px 1px black;
}
```

### truncate overflowing text

Use this snippet to truncate the overflowing text.

See result [here](https://css-tricks.com/snippets/css/truncate-string-with-ellipsis/)

```css
.overflowing {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```
