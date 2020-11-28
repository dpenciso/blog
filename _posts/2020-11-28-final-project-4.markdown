---
layout: post
title: "Final Project Week 3"
date: 2020-11-29 14:02:00 -0600
categories: homework
---

# What did I do this week?

This week was a frustrating one when it came to my code. My focus this week was to hook the front-end and back-end together so that I could directly submit from my front-end to the database. I used [MDN](https://developer.mozilla.org/) as my primary source when looking into how to best use the Fetch API. However, the problem I ran into was simply targeting my input value.

My HTML code for my title input looks like this:

    <input
        type="text"
        class="form-control title-input"
        id="title"
        aria-describedby="emailHelp"
        placeholder="Enter title"
    />

Seeing that, I wanted to target the text that users place use inside of it by using <code>querySelector</code>:

    const entryTitle = document.querySelector("#title").value;

However, when I hook it all up to my submit button, it isn't getting the text from inside of the input box. This is what is happening when I am clicking the submit button:

    const submitButton = document.querySelector(".custom-submit");
    submitButton.addEventListener("click", (event) => {
        event.preventDefault();
        console.log(entryTitle);

I've spent a couple hours doing different things. For example <code>textContent</code> and <code>innerHTML</code> instead of <code>value</code>. Using <code>getElementById</code> instead of <code>querySelector</code>. I still can't quite figure it out. So that is what I am going to still be working on going into next week.
