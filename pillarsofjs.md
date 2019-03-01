# **The Pillars of Javscript**

## **Biggest Problems w/ OOP**

*The biggest problem with OOP is inheritance.* 

Class inheritance cause a tight coupling between the current class and the ancestor of the class. What's interesting is this tight coupling is what causes the opposite of what we want: *resuable and modular code*. As a result, you slowly create your different jungle of classes and as you add inheritance, your classes get more brittle and arthritic. When you find issues or bugs, you fix it everywhere, not just in one place.

This issue is often called as the ***duplication by necessity problem***  


## **The Solution**

*“Program to an interface, not an implementation,” and “favor object composition over class inheritance.”*

With JS, there is no need to rely on classes, constructors and normal class inheritance. Prototypal Inheritance *(the type when we use functions like bind(), apply() and map())* allow for a distinction some like to refer as **OLOO (Objects Linked to Other Objects)**. This allows for any object with the same prototype to access various functions chained to a parent prototype.  

Part of what makes JS so powerful are two important fundamental topics:
1. Functional Programming ( enabled by lambdas with closure)
2. Prototype Inheritance (objects w/o classes, prototype delegation - Objects Linking to Other Objects)


### **Functional Programming**

So what's the big deal with functional programming anyway? If there were to be one thing to be highlighted, its **pure functions**. Pure functions, by definition, have something called *idempotence*. This simply means:

```
Given the same inputs, a pure function will always return the same output, regardless of the number of times the function is called
```

Why is this important though? Well, it's the reason why things can be so reusable and extremely useful for a different variety of applications. It also means that you're able to write your code declaritively, not imperatively. (You can use functions as a black box and you don't need to fully understand the complexity around it. Focus on the inputs and the results, rather than the logic for it to happen).

``` 
For example, the bind() function comes from a prototype of the object Function. No matter how many times you run the bind function with the same parameters, it will always output the same result (and in a brand new function which helps with immutability).
```

Along with reusability, it has no side effects because they do not mutate any shared state or mutable arguemnts. They do not share state or side-effects and because of it, are unlikely to cause conflict with each other or with other, unrelated portions of the application.
 ```
At the end of the day, "pure functions produce stronger guarantees of encapsulation than objects without function purity... The ability to change implementation without impacting the rest of the program, a self-documenting public interface (the function signature), independence from outside code, the ability to move code around freely between files, modules, projects, and so on."
```

### **Closures**

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