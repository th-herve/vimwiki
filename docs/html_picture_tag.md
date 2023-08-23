# picture tag

The `<picture>` tag allows to specify different images source depending on
the display screen.

```html
<picture>
  <source 
    srcset="img-zoomed-out.jpg"
    media="(min-width: 1000px)"
  />
  <source 
    srcset="img.jpg"
    media="(min-width: 600px)"
  />
  <img 
    src="img-zoomed-in.jpg" 
    alt="an image"
  />
</picture>
```
