## Functions for Reused Code

- There are two kinds of functions: pure and impure.

### Pure Functions

```js
// pure functions are predictable
// if you pass the same input twice, you will get the same output twice
// all pure functions have return statements
function add(num1, num2) {
  return num1 + num2;
}

// because this function has a return statement, we can store the return value as a variable
const sum = add(5, 6);
```

### Impure Functions

```js
// notice that this variable is defined _outside the function declaration_
const coolDivFromHTML = document.querySelector("#my-divs");

function mutateCoolDiv(words) {
  // 💥 impure function alert 💥
  // this function mutates something defined _outside the function declaration_
  coolDivFromHTML.textContent = words;

  // 💥 impure function alert 💥
  // no return statement!
}
```

```js
function getRandomNumberBetween0And10(/*💥 impure function alert 💥 no arguments! */) {
  // 💥 impure function alert 💥
  // randomness! no way to predict this
  return Math.random() * 10;
}
```

## TDD

TDD stands for test driven development. It is an approach to writing software where we write our tests first. The cycle for TDD is as follows:

- RED: Write a test that fails
- GREEN: Write enough code to get the test to pass
- REFACTOR: Improve the code while keeping the test green

When we're testing our code, we're mostly concerned with testing pure functions. Since pure functions are predictable, we use tests to confirm that given specific inputs, we get the output we expect.

For example, lets imagine we want to write an application that converts Fahrenheit to Celsius. We know off the top of our head, that 32F is 0C so we want to start by writing a test that checks that when we input 32 into our function, it returns 0. We _could_ do this manually like so:

```javascript
const check = convertToCelsius(32);
console.log(check === 0);
```

This would confirm our code works the way we want it to, but doing this for a lot of functions would litter a lot of console.logs in our code base. Instead, we will use a testing library to test our code.

Testing libraries basically do the same thing as above -- call our functions with specific input and check the output however they give us a lot of additional utilities. We can not only check if the output is equal to what we expect, we can check what data type it is, or if its null, or a boolean. The testing library we'll use is called QUnit.

```js
test("convertToCelsius should convert 32 Fahrenheit to 0 Celsius", (expect) => {
  //Arrange
  // Set up your arguments and expectations
  const expected = 0;

  //Act
  // Call the function you're testing and set the result to a const
  const actual = convertToCelsius(32);

  //Expect
  // Make assertions about what is expected versus the actual result
  expect.equal(actual, expected);
});
```

QUnit is automatically included in the Web template and you can run your tests by visiting `/test` path on your app.

### Vocabulary

| Term            | Definition                                                                             |
| --------------- | -------------------------------------------------------------------------------------- |
| TDD             | Test Driven Development - a software engineering approach where you write tests first. |
| Testing Library | A utility for writing tests                                                            |
