---
layout: post
title:  "Final Project Week 2"
date:   2020-11-06 14:02:00 -0600
categories: homework
---

# What did I do this week?

This week I added a few modifications to the HTML and CSS of my app to include numbers and a word describing each rating. In addition to adding that small touch on the front-end, I installed node and a few node packages as well in order to begin work on the backend. The packages I installed were:

- Express
- Mongoose
- Body-parser
- Nodemon
- Dotenv

Since I installed node, I had to move my HTML and CSS files into a <code>src</code> folder. I then run the following line of code in my index.js:

    app.use(express.static('src'));

That way my app knows to use the files located in my <code>src</code> folder

This week I also coded my schema for the information I will be sending to my database using MongoDB Atlas. My schema looks like this:

    const mongoose = require("mongoose");

    const EntrySchema = new mongoose.Schema({
    title: {
        type: String,
        required: true,
    },
    entry: {
        type: String,
        required: true,
    },
    grateful: {
        type: String,
        required: true,
    },
    rating: {
        type: String,
        required: true,
    },
    date: {
        type: Date,
        default: Date.now,
    },
    });

    module.exports = mongoose.model("Entry", EntrySchema);

# What is the plan for next week?

Next week I plan on continuing to work on the back-end and getting my app hooked up to my database.

# What roadblocks did I encounter?

This week the biggest roadblock I encountered was being able to add the date to a journal entry. I ended up finding <code>Date.now</code> and implemented it into my schema. Next week when I hook up my database I will test and see if it works.