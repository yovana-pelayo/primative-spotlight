# Forms and Form Data

- Sometimes we want more than just one `input` worth of information at a time.
- That's when an HTML form is useful.
- It also gives us that snappy 'hit enter to submit' behavior.
- When using forms, we will need a few additional steps:
  1. `e.preventDefault()`
  1. `const formData = new FormData(form);`

```html
<form id="dog-form">
  <input name="dog-name" />
  <input name="age" type="number" />
  <button>Submit</button>
</form>
```

```js
const dogFormEl = document.querySelector('#dog-form');

dogFormEl.addEventListener('submit', (e) => {
    // this is a line that we need in order to prevent 1996 behavior from forms
    e.preventDefault();

    // we will use a built in DOM class called FormData to get the information
    // out of the form
    const formData = new FormData(dogFormEl);

    // to get the information out of the form we use the method .get()
    // notice that the .get() function takes in whatever the `name` property is in the HTML
    const name = formData.get('dog-name');
    const age = formData.get('age');
})

```
