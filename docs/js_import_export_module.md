# Javascript modules

```javascript
// in function.js
const functionToExport = () => console.log("Function");

export { functionToExport };

// in another file .js
import { functionToExport } from "./function"

functionToExport();
```
