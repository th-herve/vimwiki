# Css basics

## Basic syntax

```css
selector {
    property: value;
}
```

## Add css to html

Three methods.

- External

Css in a separate file

```html
<head>
  <link rel="stylesheet" href="styles.css"/>
</head>
```
- Internal
 
```html
<style>
  div {
    color: blue;
  }
</style>
```
- Inline

```html
<div style=" color: blue; font-size: 12px">...</div>
```
