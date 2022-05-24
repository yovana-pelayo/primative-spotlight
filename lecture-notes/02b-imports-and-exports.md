# Imports & Exports

As our apps get more complicated, we're going to want to start to move our code into separate files to keep it more organized and easier to read. We can take advantage of the Javascript module system to do this.

A module is really just a javascript file. Modules are able to load other files and make their own functions, classes or variables available to other modules.

```js
// 📁 sayHello.js
export function sayHello(user) {
  alert(`Hello, ${user}!`);
}
```

```js
// 📁 app.js
import {sayHello} from './sayHello.js;
console.log(sayHello("Benny"))
```

## Important GOTCHA!

💥 To make import/export work, browsers need `<script type="module">` 💥

_Note: there have been lots of different implementations of modules in the Javascript language, and this current system, sometimes referred to as ES6 Modules, was only added to the standard in 2015 and only recently been widely supported by browsers and Node. As such you may see other examples online using syntax like `require("myFile.js")` -- you'll learn more about this type of module later in the course._
