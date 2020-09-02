---
layout: post
title:  "Functions, Objects, and Arrays"
date:   2020-09-01 14:02:00 -0600
categories: homework
---
# What is a JavaScript function?

Functions are something that a developer will work with every day. A function is a block of code that is created to do a specific task. There are three main parts to a JavaScript function. They are:
- The name of the function
- The function parameters
- The statements that will define what the function does

A function could look something like this:

    function functName(parameters) {
        statements
    }

Something developers will see and use is a callback function. A callback function is a function that is passed into another function as an argument to be used later to complete an action.

A promise, in JavaScript, is an object that will produce a value in the future. The value will either be a resolved or failed one depending on the code after the promise.

# What are JavaScript objects?

Objects are a JavaScript data type which is used to store various information. This information can be a string, a number, variables, and even functions. An object could look like this:

    person {name: 'David', age: 25, occupation: 'Student'}

To loop through an object, one would use something called a for...in loop. Essentially what this loop does is take each item in an object and return it and its value.

# What are JavaScript arrays?

Arrays are seen everywhere in JavaScript. An array an object similar to a list. For example I could have an array called "fruit" and it would have values inside of it such as "apple", "orange", "grape", and "cherry".

    let fruit = ['apple', 'orange', 'grape', 'cherry']

Arrays are not only limited to holding strings. They can also contain numbers, functions, and even other arrays. To access the values inside of an array, you would type the array name followed by its index surrounded in brackets. For our fruit example, it would look like:

    fruit.[0]
    'apple'

A couple of ways to loop through an array are to use simple <code>for</code> and <code>while</code> loops.

# What have I learned this week?

This week I learned what a promise is. Prior to this week I had heard the term promise but had no idea what it was. In order to learn about it I used MDN which had plenty of information about what promises are and how to use them.