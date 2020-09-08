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
            console.log(x)
            example(-1)
    }
    example(10)