# Javascript modules

```javascript
// in function.js
const functionToExport = () => console.log("Function");

export { functionToExport };

// in another file .js
Import { functionToExport } from "./function"

functionToExport();
```
