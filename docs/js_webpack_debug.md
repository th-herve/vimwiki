# Javascript webpack debug

Track error more easily by enabling debug option.

In webpack.config.js add `mode: "development"`
And `devtool: "inline-source-map"`

inline-source-map allows to track the file in which the error occurs.

```javascript
 const path = require('path');
 const HtmlWebpackPlugin = require('html-webpack-plugin');

 module.exports = {

+ mode: 'development',                        +
   entry: {
     index: './src/index.js',
     print: './src/print.js',
   },
+  devtool: "inline-source-map",              +
   plugins: [
     new HtmlWebpackPlugin({

+     title: 'Development',                   +
     }),
   ],
   output: {
     filename: '[name].bundle.js',
     path: path.resolve(__dirname, 'dist'),
     clean: true,
   },
 };
```
