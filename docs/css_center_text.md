# Css center text

## Horizontal alignment

## text-align

```html
<div class="container"> 
  <h1>Center this title!</h1> 
</div> 
```
```css
.container { 
  text-align: center; 
}
```

## margin

```html
<div class="container"> 
  <h1>Heading</h1> 
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean faucibus urna et turpis tempus pulvinar. Vestibulum laoreet lectus eget egestas mattis. Donec et leo consectetur, elementum est ac, aliquet nisl. Nunc aliquet, est sollicitudin suscipit auctor, lacus erat mattis ex, id bibendum lorem neque vitae mauris. Ut et tellus lectus. Maecenas non enim eget ante semper accumsan in at mi. Nam iaculis nec ex sed sodales. Morbi id euismod sapien.</p> 
</div> 
```

```css
.container { 
  margin: auto; 
  width: 450px; 
} 
```

## Vertical align

## line-heigh

```html
<div class="container"> 
  <p>This is some text</p> 
</div> 
```
```css
.container { 
  width: 450px; 
  height: 200px; 
  line-height: 200px; 
} 
```

## padding

By setting the same amount of y padding on the container, it pushes it to grow with the text centered.

```css
.text-container { 
  background-color: green; 
  width: 450px; 
  padding: 60px 0; 
} 
```
