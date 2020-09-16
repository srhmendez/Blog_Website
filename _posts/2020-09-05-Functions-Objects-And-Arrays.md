---
layout: post
title: Functions, Objects Arrays Oh My!
image: https://miro.medium.com/max/1400/1*Ahomp1dXE5Ofb6Fgh_7WDA.jpeg
categories: Web_Development
---
![JavaScript](https://miro.medium.com/max/1400/1*Ahomp1dXE5Ofb6Fgh_7WDA.jpeg)


# Functions, Objects & Arrays Oh My!

## What are functions in Javascript?

Functions are a "subprogram" that can be called by code. The function has three parts. 

1. The function declaration
2. The parameters
3. The function Statement.

They look something like this:
```
let myFunction = function() {
    statements
}
```
Although you are able to write anonymous functions, it is preferred to always give your function a name. The reason for this is so that when you are in the process of finding an error, you are able to see the name of the function making it a lot easier to find the mysterious error.

Functions with names look like this:
```
let myFunction = function namedFunction(){
    statements
}
```

## How are they used and defined?

Functions are used when they are called. So first you have to define a function like the one below
```
let myFunction = function namedFunction(a, b){
    c = a * b
    return c
}
```
Then when you are ready to execute the code, you must call it. When you call a function, you type its name and then you pass what are called parameters in the paranthesis. See the example below.
```
let x = myFunction(2, 5)
```
After passing the code that you see above, it would return a value of 10. As you can see from myFunction above, the statements are executed with the parameters we declared for x.

These parameters are local to the function only and are not stored in the function after it returns a value of 10. 

In this sense, you are able to use the same function to run different parameters. 

## What is a callback function?

A call back function is simply a function passed into another function as an argument. 

The code below is an example of a callback function. The processUserInput function is called and passes the function called greeting as an argument.
```
function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  let name = prompt('Please enter your name.');
  callback(name);
}

processUserInput(greeting);
```

Callbacks are also used to continue executing code after an asynchronous operation has completed. These types of callback are called asynchronous callbacks. This type of callback is often used in a .then() block of code that is attached to the end of a promise after that promise either completes or rejects. This asynchronous function is used to connect to many modern web APIs.

## How do you use promises in functions?

A promise is an object that represents an eventual completion or a eventual failure of an asynchronous operation.

A promise is a returned object that you are able to put in callback functions.

Promises simplify and clean up code by reducing the amount of lines and characters needed.

If createAudioFileAsync() were rewritten to return a promise, using it could be as simple as this:
```
createAudioFileAsync(audioSettings).then(successCallback, failureCallback);
```
That's shorthand for:
```
const promise = createAudioFileAsync(audioSettings); 
promise.then(successCallback, failureCallback);
```
## What are objects in Javascript

An object is a collection of properties and a property and a property is an association between a name (or key) and a value.

A property's corresponding value can be function, which is also known as a method.

Some objects are predeifined in the browser, but you are also able to create your own objects.

## How are they used and defined?

In the example below, the object created is assigned the name of myCar. The properties, known as keys, of myCar are make, model, and year. The values associated are Ford, Mustang, and 1969.
```
let myCar = new Object();
myCar.make = 'Ford';
myCar.model = 'Mustang';
myCar.year = 1969;
```
to access the properties within the object myCar above, you can use what is called dot notation. It look like the example below.
```
objectName.propertyName
```
To access the make of myCar you would use dot notaiton as follows:
```
myCar.make
```
You can also define or set properties of an object using brackets and the assignment operator as shown below:
```
myCar['make'] = 'Ford';
myCar['model'] = 'Mustang';
myCar['year'] = 1969;
```
## How do you loop through an object?

You can use bracket notation with for...in to iterate or loop through all the properties of an object as shown in the example below.
```
function showProps(obj, objName) {
  letresult = ``;
  for (let i in obj) {
    // obj.hasOwnProperty() is used to filter out properties from the object's prototype chain
    if (obj.hasOwnProperty(i)) {
      result += `${objName}.${i} = ${obj[i]}\n`;
    }
  }
  return result;
}
```
## What are Arrays in Javascript?

Arrays are list-like objects that have methods that can perform traversal and mutation operations. Aspects like length alongside element type of arrays are not fixed. They can easily be changed and manipulated using array methods.

Arrays cannot use strings as element indexes, they must use integers as element indexes. Setting and accessing the element indexes using dot or bracket notation will not set or retrieve an element from the array list itself, but will set or access a variable associated with that specific array's object property collection. This object property collection is completely separate from the list of elements. This means that array's traversal and mutational operations cannot be applied to the properties themselves.

## How are they used and defined?

Arrays are created as shown below: 

>let fruits = ['Apple', 'Banana']

The array is called fruits and the properties are Apple and Banana.

You can access the fruits properties using bracket notation and integers associated with the index of the item that you need.
```
let first = fruits[0]
// Apple
```
## What are 2 ways to loop though an array?

The way shown below returns a new array iterator object that contains the values for each index within the desired array.
```
Array.prototype[@@iterator]()
```
You can also loop through an array using the forEach method as shown below:
```
fruits.forEach(function(item, index, array) {
  console.log(item, index)
})
```

## Write about at least one other thing you learned this week.

I learned more about arrow functions because I realized the syntax of arrow functions are hard for me to understand. We went over a few points in class, but I went and did some extra reading on MDN to solidify the concepts I was curious about.
 ```
(param1, param2, …, paramN) => { statements } 
(param1, param2, …, paramN) => expression
// equivalent to: => { return expression; }

// Parentheses are optional when there's only one parameter name:
(singleParam) => { statements }
singleParam => { statements }

// The parameter list for a function with no parameters should be written with a pair of parentheses.
() => { statements }
```