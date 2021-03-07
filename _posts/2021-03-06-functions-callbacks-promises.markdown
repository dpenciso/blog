---
layout: post
title: "Functions, Callbacks, and Promises"
date: 2021-03-06 14:02:00 -0600
categories: homework
---

## Functions

# How to declare a function.

There are different ways to declare a function. Here are three:

```
function name() {}
```

```
const name = function() {}
```

```
const name = () => {}
```

# How to return a value from a funciton.

To return a value from a function, put <code>return</code> followed by the thing you want to return inside of the funtion like so:

```
const name = () => {
    let x = 1
    return x
}
```

# How to accept a value into a function.

In order to accept a value into a function, you must put the value inside of the parentheses like so:

```
const name = (x) => {
    return x + 1
}
```

## Callbacks

# What is a callback?

A callback is a function that is passes as an argument to another function. This allows the callback funtion to be called inside of another function.

# How do they work?

Here is an example of how a callback function would work:

First you would write two functions. One being the callback function and the other with the callback as a parameter

```
function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}
```

Then you would call that function with the desired callback function passes as the parameter

```
processUserInput(greeting);
```

# When might you use one in your own code?

You might use a callback in your own code when you want to make sure that one function is executed before another.

## Promises

# What is a promise?

A promise is an object that is essentially pending and it will come back with a value when the promise has been resolved or completed.

# How do they work?

When a promise is called, it takes a function that will be ran immediately and it passes in two functions as parameters. One of these is a resolve and the other a reject. The resolve is what is returned when the promise is fulfilled. The reject is what is returned when the promise is rejected or has an error. For example:

```
let thisPromise = new Promise(function(resolve, reject) {
  resolve();
  reject();
});
```

After declaring this promise, you must use it in the code like this for example:

```
thisPromise.then(
    function(value) {
        console.log(value)
    }
    function(error) {
        console.log(error)
    }
)
```

# When might you use one in your code?

You might use a promise in your own code when handling asynchronous operations since it will easily handle these operations and the errors in an efficient way. For example:

```
let promise = new Promise(function(resolve, reject) {
  setTimeout(() => resolve("done!"), 1000);
});

promise.then(
  result => alert(result)
  error => alert(error)
);
```

In this case, only the first funciton will run and it will display "done!" after 1 second. Since the promise was fulfilled, the error will not run.

# What is the async, await syntax and how does it work?

The async, await syntax is as follows:

```
async function example() {
  let result = await something
  return result
};
```

This turns the function into a promise wiithout using the <code>Promise</code> keyword and having to use <code>.then</code> throughout the code.

# Why is the async, await syntax helpful?

I have found that the async await syntax is most helpful whe making API calls because this allows the function to run while waiting to reach out and fetch information from the API. Once it is received, it is used. Async, await is simple, clean, and effective.