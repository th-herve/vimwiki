# Javascript using dotenv

```javascript
// install from cli
npm i dotenv

// import 
require('dotenv').config();
// or if ES6
import dotenv from 'dotenv'
dotenv.config();

// test it
console.log(process.env);

// access
const token = process.env.APP_TOKEN;
```
