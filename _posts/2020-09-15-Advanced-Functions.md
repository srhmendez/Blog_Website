---
layout: post
title: Advanced Functions
image: https://images.pexels.com/photos/34153/pexels-photo.jpg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260
categories: Web_Development
---
![JavaScript](https://images.pexels.com/photos/34153/pexels-photo.jpg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260)


# Advanced Functions

## What is recursion?

Recursion is the act of a functino calling itself. It is often used to solve problems that have their own internal problems to solve. 

A recursive function can recieve two inputs:
1. a base case (This is the case that would end the recursion)
2. a recursive case (This is a case that would resume the recursion)

The example below is a very simple function that gives you a good idea of what a recursive function looks like
and how it operates.

```
def recurse(x):
  if x > 0:
       print(x)
       recurse(x - 1)

recurse(10)
```

## What are Scopes and Closures in Javascript?

A Scope is a reference to the current context of code, which determines what variables are available to the function. There are two different kinds of Scope, global and local. global variables are declared outside the block of code while local variables are declared inside of the block.

Below is an example to demonstrate the difference between global and local scopes. You can see the variable species is named the same (species), but assigned different values in and out of a function. 
'''
// Initialize a global variable
var species = "human";

function transform() {
  // Initialize a local, function-scoped variable
  var species = "werewolf";
  console.log(species);
}

// Log the global and local variable
console.log(species);
transform();
console.log(species);
'''

When looking at the output, you notice that although the specied variable has the same name in and out of the function, it produces different values in and out of the function. This is a great demonstration of local vs global scopes.
'''
Output
human
werewolf
human
'''

A Closure is a function enclosed or packaged together with references to its Lexical Environment. What this means is that a Closure gives you access to an outer function's Scope from an inner function. 

A closure is a function having access to the parent scope, even after the parent function has closed. The example below demonstrates this. The function assigned to add is ran once, setting the counter to 0 and it then returns a function to be assigned to the add variable for future use. The great thing about closure is that since it can access the parent scope, in this example, the new function assigned to the add var still knows that the counters value is 0 although it has already been run. 
'''
var add = (function () {
  var counter = 0;
  return function () {counter += 1; return counter}
})();

add();
add();
add();

// the counter is now 3
'''

## Why is understanding scopes and closures important?

Closures are important because they control what is and isn't in the scope of a particular function. Closures also control what variables are and are not available or shared between sibling and parent functions in the same scope. It is important to understand how variables and functions relate to each other so that you know what is occuring in any given block of code. 

Closures are also often used in JavaScript when it comes to Data Privacy. In event handlers, callbacks, partial applications, and in currying and other programming patterns. 

"In JavaScript, closures are the primary mechanism used to enable data privacy. When you use closures for data privacy, the enclosed variables are only in scope within the containing (outer) function. You can’t get at the data from an outside scope except through the object’s privileged methods. In JavaScript, any exposed method defined within the closure scope is privileged." - "Mastering the JavaScript Interview", Eric Elliot 

## What is the Spread Operator?
The spread operator looks like this... No, seriously. it looks like this:
'''
...
'''
So what does it do?

Spread operators allows an iterable like an array expression or a string to be expanded in places where zero or more arguments (for function calls) or elements (like array literals) are expected.

'''
var mid = [3, 4];
var arr = [1, 2, ...mid, 5, 6];
'''
'''
Output:
[1, 2, 3, 4, 5, 6]
'''

## When is it useful?

One benefit of the spread operator is that it creates a new reference to it's primitive values, aka it copys them and returns a new reference. It is useful to create new instances of arrays that behave in the desired way rather than relying on a spread's primitve values that can behave unexpectedly depending on how you need to use them. It is a great way to prevent unnecessary errors when passing values.