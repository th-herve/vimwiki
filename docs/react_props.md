# React props

Props allow to pass argument to react component.

```javascript
function Button({ text, color, fontSize }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return <button style={buttonStyle}>{text}</button>;
}

export default function App() {
  return (
    <div>
      <Button text="Click Me!" color="blue" fontSize={12} />
      <Button text="Don't Click Me!" color="red" fontSize={12} />
      <Button text="Click Me!" color="blue" fontSize={20} />
    </div>
  );
}
```
## Default props

```javascript
function Button({ text = "Click Me!", color = "blue", fontSize = 12 }) {
  const buttonStyle = {
    color: color,
    fontSize: fontSize + "px"
  };

  return <button style={buttonStyle}>{text}</button>;
}
```

## Function as props

```javascript
function Button({ handleClick }) {

  return (
    <button onClick={() => handleClick('https://www.theodinproject.com')}>
      click me
    </button>
  );
}

// if there is no argument to pass, there is no need for anonymous function:
  return (
    <button onClick={handleClick}>
      click me
    </button>
  );

```
