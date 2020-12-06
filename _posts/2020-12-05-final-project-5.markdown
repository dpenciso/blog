---
layout: post
title: "Final Project Week 5"
date: 2020-12-04 14:02:00 -0600
categories: homework
---

# What did I do this week?

This week was a great week for my journal app. It began with a peer looking at my code and making a suggestion to help my input post to my database. The solution was actually quite simple. Sometimes it just takes someone else looking at your code for you to realize the solution. So thank you Tyson! The solution to my problem was to simply set <code>entryTitle = documeunt.querySelector('#title')</code> outside of the click event and <code>entryTitle.value</code> inside of it.

After getting the values to <code>console.log</code>, I had to make sure that my values would correctly post to my database. I struggled to find the solution as to why my code wasn't posting to my database since I was able to console log it correctly. The issue was that in my server code, I was using <code>req.query</code> instead of <code>req.body</code>. <code>req.query</code> is supposed to contain URL query parameters which I did not have since I am using a form. My new code below uses <code>req.body</code> to post the input from the form:

    {
        title: req.body.title,
        entry: req.body.entry,
        grateful: req.body.grateful,
        rating: req.body.rating,
        date: req.body.date,
    }

Finally progress. I kept the ball rolling this week by getting previous posts and displaying them below the form you use to make a new post. I retrieved the information by using an <code>async function</code> that looks like this:

    async function getEntries() {
    let url = '/entries';
    try {
        let res = await fetch(url);
        return await res.json();
    } catch (error) {
        console.log(error);
    }
    }

After retrieving the information, I needed to display it. I decided a good way to go would be to use Bootstrap's card component. For each entry I decided to include the title of the entry, the date, the content, and the rating. I thought that perhaps rendering the whole post to the card would be a little too much text to take in, so I decided to use the <code>splice()</code> in order to only include the first 50 characters of each post. I then saw that my posts were rendering in the order of oldest first. I think that users would prefer having their most recent posts first so I decided to sort them by most recent date using <code>reverse()</code>. My final code for rendering past posts looks like this:

    async function renderEntries() {
    let entries = await getEntries();
    let sortedEntries = entries.reverse()
    let html = '';
    sortedEntries.forEach(entry => {
        let htmlSegment = `<div class="card custom-card" style="width: 18rem;">
        <div class="card-body">
            <h3 class="card-title">${entry.title}</h3>
            <h5 class="card-title">${entry.date.slice(0,10)}</h5>
            <p class="card-text">${entry.entry.slice(0,50)}...</p>
            <h6 class="card-subtitle mb-2 text-muted">Rating: ${entry.rating}</h6>
            <a href="#" class="card-link">View/Edit</a>
        </div>
        </div>`;
        html += htmlSegment;
    });

    let loadedEntries = document.querySelector('.loadedEntries');
    loadedEntries.innerHTML = html;
    }

    renderEntries();


# What is the plan for next week?

Next week I need to finish up the app by allowing the user to click on the card containing a previous post and pull up the whole post for viewing and editing. I'm still debating whethere or not to include the editing part of the app since I think journaling is something that should be permanent. If you have any thoughts on that let me know.

# What roadblocks did I encounter?

This week was full of roadblocks but the biggest was probably making sure that the information from the form was posting to the database. It was important for me to reach out to others to get help looking over my code.
