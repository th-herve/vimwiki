# React state

State allows to keep track of component state, and dynamically change them.

Use the `useState` hook to define state. It takes an initial value as a parameter and returns an array with two elements that we can destructure to get:

1. The current state value
2. A function to update the state value

Import `useState` from react to use it.

```javascript
import { useState } from 'react';

const [stateValue, setStateValue] = useState(initialValue);

// example to set the background color 
const [backgroundColor, setBackgroundColor] = useState(initialColor);

// In a component (not really correct)
function Button() {
  const [backgroundColor, setBackgroundColor] = useState(initialColor);
  const onButtonClick = (color) => () => {
    setBackgroundColor(color);
  };
  return (
    <button style={{ backgroundColor, }} onClick={onButtonClick(color)} ></button>  
  );
}
```
>Note: hook can only be called at the top level of the component, meaning not inside condition, loop or other nested function.
