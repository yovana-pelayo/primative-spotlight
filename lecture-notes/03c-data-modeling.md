# Data Modeling

Up until now our state has mostly consisted of primitive values i.e. numbers, strings, booleans but what if our app wants to track information that is more complicated than that?

For example, lets imagine an app that keeps track of your pets. You could simply store the name of each pet, but that wouldn't make for a very interesting application. Instead, we likely want to keep track of lots of different features of that pet such as their name, their age, or their breed. While we could store each of those items in their own variable, it is more convenient and powerful to keep them all together in a single object:

```js
const pet = {
  name: "Benny",
  age: 6,
  breeds: ["Terrier", "Chihauhau", "Pekingese"],
};
```

This process of extracting the information we want to store about a real life thing and converting is to an object with attributes and values is a form of "data modeling". Data modeling is the act of taking a real world thing, and deciding out how to represent it using code. What properties does it contain that we will want to present to the user?
