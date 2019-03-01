# Scopes & Closures in Javascript

## **Scope**



## **Closures**
Like objects, closures are a mechanism for containing state. In JS, closure is created when a function access a variable outside of its immediate function scope.

For example:

``` javascript
var counter = function counter() {
  var count = 0;
  return {
    getCount: function getCount() {
      return count;
    },
    increment: function increment() {
      count += 1;
    }
  };
};
```
You can use closure to create data privacy and it's really simple to create: 

 *Define a function within another function then expose the inner function (by returning it or passing it into another function)*

The end result of closure is access to the variables from the inner function even if has finished running. By default, variables are removed from JS when they are inside a function and the function has finished executing. 