# React useRef

## Using useRef to access element created by a loop

```javascript
// initialize the ref with an empty object
const itemEls = useRef({});

// create the items and add them to the ref object
{items.map((item, index)) => (
 <p key={item} ref={(element) => itemEls.current[index] = element}>{item}</p>
));
```

[More info](https://mattclaffey.medium.com/adding-react-refs-to-an-array-of-items-96e9a12ab40c)
