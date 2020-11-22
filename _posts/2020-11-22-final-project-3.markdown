---
layout: post
title:  "Final Project Week 3"
date:   2020-11-22 14:02:00 -0600
categories: homework
---

# What did I do this week?

This week was a rough week for my family. We all got sick and my 18-month old son started pushing through his molars. That being said, I didn't get around to nearly as much code as I wanted to this week since I was trying to recover my strength and take care of my wife and son. The two biggest things I accomplished this week were connect to my database (MongoDB Atlas), and set up my storage operations (CRUD).

In order to connect to my database, I used the following line of code:

    mongoose.set("useFindAndModify", false);
    mongoose.connect(
    process.env.DB_CONNECT,
    { useNewUrlParser: true, useUnifiedTopology: true },
    () => {
        console.log("Connected to db!");

        app.listen(port, () => console.log(`Listening on port ${port}...`));
    }
    );

The <code>process.env.DB_CONNECT</code> points to my <code>.env</code> file where I keep the URL and password that will connect my application to my database. I do this so that I can include that file in my <code>.gitignore</code> file so that my URL and password are not made public when I push my application to GitHub. I also chose to <code>app.listen</code> in this function so that if the application runs, I know that it is connected to my database.

The following is my code for my storage operations:

POST:

    app.post("/entries", (req, res) => {
    Entry.create(
        {
        title: req.query.title,
        entry: req.query.entry,
        grateful: req.query.grateful,
        rating: req.query.rating,
        date: req.query.date,
        },
        (err, entries) => {
        if (err) console.log(err);

        Entry.find((err, entries) => {
            if (err) console.log(err);

            res.json(entries);
        });
        }
    );
    });

GET:

    app.get("/entries", (req, res) => {
    Entry.find((err, entries) => {
        if (err) console.log(err);

        res.json(entries);
    });
    });

PUT:

    app.put("/entries/:id", (req, res) => {
    Entry.findById(req.params.id, (err, entry) => {
        entry.update(req.query, (err, entries) => {
        if (err) console.log(err);

        Entry.find((err, entries) => {
            if (err) console.log(err);

            res.json(entries);
        });
        });
    });
    });

DELETE:

    app.delete("/entries/:id", (req, res) => {
    Entry.remove(
        {
        _id: req.params.id,
        },
        (err, entries) => {
        if (err) console.log(handleError(err));
        Entry.find((err, entries) => {
            if (err) console.log(handleError(err));
            res.json(entries);
        });
        }
    );
    });

These were pretty simply. I just had to remember that for the PUT and DELETE operations, I needed to include the id so that only that specific entry was updated or deleted.

# What is the plan for next week?

Next week I plan on hooking up the front-end to the back-end.

# What roadblocks did I encounter?

Honestly, the biggest roadblocks that I encountered this week were just having the energy and time to work on the project since I was battling being sick and a teething child. Code-wise, the biggest roadblock was making sure that the database was hooked up properly. Putting the <code>app.listen</code> in the database function definitely helped though.