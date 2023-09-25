# srcset

The `srcset` attribute of the `img` tag allows the browser to choose between
`different version` of the `same image` by varying its size.

It allows `responsive design` and/or `increase performance`.

```html
<img
  srcset=""
  src=""
  alt=""
>
```
It is used by specifying a coma separated list of images, follow by the size
they should be used with.

```html
// use with the width of the image + sizes, here 70vmin means 70% of the viewport min width. 300w, 600w... are the width of the images (300px, 600px...)
<img 
  alt="A baby smiling with a yellow headband."
  srcset="
    baby-s.jpg  300w,
    baby-m.jpg  600w,
    baby-l.jpg  1200w,
    baby-xl.jpg 2000w
  "
  sizes="70vmin"
>
// use with the x means the pixel density
<img 
  alt="An image"
  src="my-image.png"
  srcset="
    my-image.png 1.5x,
    my-image-2.png 2x,
    my-image-3.png 3x,
    my-image-4.png 4x,
    my-image-100.png 100x
  "
>
```

