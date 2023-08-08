# Jest

Jest allows to write and execute test.

## Set up

```bash
npm install --save-dev jest

# To use ES6 module import statements:
npm install --save-dev babel-jest @babel/core @babel/preset-env

```

In package.json:

```json
{
  "scripts": {
    "test": "jest"
  }
}
```
Create a babel.config.js in the root dir

```json
module.exports = {
  presets: [['@babel/preset-env', {targets: {node: 'current'}}]],
};
```

## Usage

[List of expression](https://jestjs.io/docs/getting-started#using-babel)

Create a `.test.js` version of the `.js` file to test.

For example: sum.js -> sum.test.js

In the .test.js file:

```javascript
import { functionToTest } from './sum.js'

test('Write comment here', () => {
  expect(functionToTest(argument)).toBe('expected result');
});
    
// example:
test('Test if string is capitalize', () => {
  expect(capitalize('Test')).toBe('TEST');
});
```

Then run `npm test`
