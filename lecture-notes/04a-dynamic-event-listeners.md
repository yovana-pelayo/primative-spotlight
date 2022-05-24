# Dynamic Event Listeners

Up until now, all of our event listeners have been defined on page load. In other words, the DOM elements that we want to track events on are available when we first open our app. But we know we have the ability to add new DOM elements to the page. What if we want to add event listeners to those new elements?

## Dynamic Event Listeners

Event Listeners are just like any other property - they can be added on to DOM elements you create.

```js
const div = document.createElement("div");
div.textContent = "I will alert you when clicked";
div.addEventListener("click", (e) => {
  alert("You clicked the div!");
});
```

This is especially helpful in games when elements will be added an removed from the page depending on the user's actions.
