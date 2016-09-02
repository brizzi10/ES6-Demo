# ES6-Demo
Arrow functions, Default Parameters, Shortening Properties and Methods

###Arrow functions
An arrow function is an anonymous function expression that doesn't change the value of `this`.

When one wants to call the `this` function repeatedly over the course of your code, using an arrow function is a way to execute functions without throwing that off or needing to save `this` to a variable.

For example:

```
function Person() {
  this.age = 0;

  setInterval(function growUp() {
    this.age++;
  }, 1000);
}
```
In this code, the first `this` is referring to the Person object, but the second `this` is instead referring to the growUp function. That means it won't be able to find the age value, and this whole thing won't work like it's supposed to.

The old way of fixing this would involve saving a reference to `this` early on:
```
function Person() {
  var person = this;
  person.age = 0;

  setInterval(function growUp() {
    person.age++;
  }, 1000);
}
```
But now, the arrows can help you sidestep this problem entirely.
```
function Person() {
  this.age = 0;

  setInterval(() => {
    this.age++;
  }, 1000);
}
```
Now, the arrow function runs the function without creating its own context for `this`, and the age value should increase as intended.

Arrow function expressions don't work especially well in method functions, though. You shouldn't worry about them if you're not working with non-method functions.
