# Pillars of Javscript

## Biggest Problems w/ OOP

*The biggest problem with OOP is inheritance.* 

Class inheritance cause a tight coupling between the current class and the ancestor of the class. What's interesting is this tight coupling is what causes the opposite of what we want: *resuable and modular code*. As a result, you slowly create your different jungle of classes and as you add inheritance, your classes get more brittle and arthritic. When you find issues or bugs, you fix it everywhere, not just in one place.

This issue is often called as the ***duplication by necessity problem***  


## The Solution

*“Program to an interface, not an implementation,” and “favor object composition over class inheritance.”*

With JS, there is no need to rely on classes, constructors and normal class inheritance. Prototypal Inheritance *(the type when we use functions like bind(), apply() and map())* allow for a distinction some like to refer as **OLOO (Objects Linked to Other Objects)**. 

Part of what makes JS so powerful are two important fundamental topics:
1. Functional Programming ( enabled by lambdas with closure)
2. Prototype Inheritance (objects w/o classes, prototype delegation - Objects Linking to Other Objects)

### Closures

Like objects, closures are a mechanism for containing state. In JS, closure is created when a function access a variable outside of its immediate function scope.