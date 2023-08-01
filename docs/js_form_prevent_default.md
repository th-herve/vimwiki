# Javascript form prevent default

```javascript
const form = document.querySelector('form');

function handleFormSubmission(event) {
  event.preventDefault();
  
  const form = event.target;
  const formData = new FormData(form);
  
  const name = formData.get('name');
  const age = formData.get('age');
  ...
}

form.addEventListener('submit', handleFormSubmission);
```
