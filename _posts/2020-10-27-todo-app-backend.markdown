---
layout: post
title:  "Todo App Backend"
date:   2020-10-27 12:02:00 -0600
categories: homework
---

## Todo App Backend

# How did I design/architect my app and server?

My ToDo app is designed around using EJS as a templating engine and MongoDB as my database. I use Mongoose so that I have access to schemas and store the information I store from the todo is: the todo itself, its category, and the date.

# How did the front end connect to the backend?

The front end connects to the backend through EJS reaching out to the endpoints in my index.js file where I make those calls.

# Why did I choose the design I did?

I chose my design because it seemed nice to be able to interact with both the front-end and back-end at the same time through the templating engine. My initial ToDo app wasn’t well structured and I would have to restructure a lot in order to get it to work. Working with both at the sime time, seemed like the most efficient thing to do.

# How did you model you data and why?

I modeled the data by taking the name of the ToDo, its category, and the date it was posted and storing those in the database. I did it that way because that way all the information would be stored together.

# Why is documentation important?

Documentation is important because it allows others to see how you developed your product. It really gives logic to your code and explains why you did the things you did.