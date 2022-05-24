# Render Functions

- Consider this HTML.
  - What's annoying about it?
  - Would you enjoy writing HTML that looked like this?

```html
<div class="dog">
  <p>Fido</p>
  <img src="www.puppy.com/32.png" />
</div>
<div class="dog">
  <p>Codi</p>
  <img src="www.puppy.com/11.png" />
</div>
<div class="dog">
  <p>Spunky</p>
  <img src="www.puppy.com/25.png" />
</div>
```

- Notice that we're writing the same div several times with small differences.

- For a number of reasons, you should avoid writing the same HTML over and over again.
- When you're in a situation like this, it's nice to write a function that can write our HTML for us!

```js
export function renderDog(dog) {
  const div = document.createElement("div");
  const img = document.createElement("img");
  const p = document.createElement("p");

  div.classList.add("dog");

  p.textContent = dog.name;
  img.src = dog.url;

  div.append(p, img);

  return div;
}
```

- `renderDog()` returns some an HTML element that looks like this:

```html
<div class="dog">
  <p>Fido</p>
  <img src="www.puppy.com/32.png" />
</div>
```

- We can call and use this function like so:

```js
// grab a hard coded DOM element from the HTML
const container = document.querySelector('#container);

// make a dog object
const dog = {
    name: 'Fido',
    url: 'www.puppy.com/32.png',
};

// feed the dog object to the renderDog function.
// This function returns a DOM node
const dogEl = renderDog(dog);

// append this DOM node to the hard-coded DOM we grabbed upstairs.
container.append(dogEl);
```

We can also write tests for this type of function because it is pure. It accepts an object and returns an element. To test render functions, we will use the attribute `outerHTML` which returns a string representation of the DOM element.

```js
test("renderDog returns a <div> element", (expect) => {
  //Arrange
  // Set up your expected HTML output
  const expected = `<div class="dog"><p>Fido</p><img src="www.puppy.com/32.png" /></div>`;

  //Act
  // Call the function you're testing and set the result to a const
  const dog = {
    name: "Fido",
    url: "www.puppy.com/32.png",
  };
  const actual = renderDog(dog);

  //Expect
  // Make assertions about what is expected versus the actual result
  // For render functions we will check the outerHTML attribute
  expect.equal(actual.outerHTML, expected);
});
```
