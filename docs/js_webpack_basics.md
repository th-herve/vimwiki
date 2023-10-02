# Javascript Webpack basics

Webpack creates a bundle of the code for a project. It compiles 
all our javascript files into a single file.

The code is gonna be written in the directory `src` and result in
a single file `main.js` in the `dist` directory.

## Basics

### Set up

1. Inside the root of the project.
    ```bash
    npm init -y
    npm install package-name
    ```
2. Create a `src` directory
3. Write javascript in `src`
4. Create a `dist` directory for distribution
5. Run
    > npx webpack
6. `main.js` should be generated in `dist`

## Configuration

Each project can have a configuration file for webpack.

In the root of the project create `webpack.config.js`

```javascript
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist'),
  },
};
```

Run:
> npx webpack --config webpack.config.js

[source](https://webpack.js.org/guides/getting-started/)
