---
layout: post
title:  "Advanced Functions"
date:   2020-09-08 14:02:00 -0600
categories: homework
---
# What is recursion?

Recursion, simply put, is a function that continues to be called until a certain condition is met. This can be useful when you need to run a function multiple times and need it to stop after a certain number of times. A recursive function always has a condition that stops the function from calling itself. An example of a recursive function is:

    function example(x) {
        if (x > 0)
            console.log(x);
            example(-1);
    };
    example(10);

In this example, the function “example” is called only while x > 0. Once that condition is met, the function will stop calling itself. The output of this function would be: 10, 9, 8, 7, 6, 5, 4, 3, 2, 1.

# What are scopes and closures in JavaScript?

Scopes, in JavaScript, refer to the current context of the code. That is to say, what variables are available in the code I am using at the moment. There are two kinds of scope: global and local. Global variables are those that are declared outside of a block of code and are therefore available everywhere. Local variables are those declared inside of a block of code and are only available inside of that particular block.

An example that displays these different scopes is:

    let myVariable = 'global';

    function localVariable() {
        let myVariable = 'local';
        console.log(myVariable);
    };

    console.log(myVariable);
    console.log(localVariable);

In this example, the first console.log call will return 'global' and the second will return 'local'.

Closures in JavaScript simply mean that a function that is inside of another function has access to the outer functions variables.

# Why is it important to understand scopes and closures?

It is important to understand scopes and closures when using JavaScript because without that understanding, you will find yourself not being able to access functions and variables when you need them.

# What is the spread operator?

The spread operator(which is displayed as …) allows an utterable such as an array to be expanded in places where zero or more arguments are expected. For example:

    let arr1 = [1,2,3];
    let arr2 = [...arr1];

    arr2.push(4);

    console.log(arr1);
    console.log(arr2);

The output of this example would be:

    [1,2,3]
    [1,2,3,4]

In this example, I took arr2 and assigned it the value of arr1. I then added the number 4 to the end of arr2 through the push method and kept arr1 the same. If I had not used the spread operator, arr1 would also be changed.

# When is the spread operator useful?

The spread operator is useful when you have a variable based off another variable and you only want to change one of the variables.