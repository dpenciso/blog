---
layout: post
title: "Final Project Week 5"
date: 2020-12-13 14:02:00 -0600
categories: homework
---

# What did I do this week?

This week I found a way display the previous journal entries. The way I did that was to integrate a modal from Bootstrap to allow the user to click on the preview of the journal entry and then have the entry come up in a modal. In the modal, I have the title, date, and rating of the journal entry in the header, and then the content of the entry in the body. The current code looks like this:

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

                <button type="button" class="btn btn-outline-primary btn-sm" data-toggle="modal" data-target="#exampleModalCenter${entry.date}">
                View Entry
                </button>

                <div class="modal fade" id="exampleModalCenter${entry.date}" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
                <div class="modal-dialog modal-dialog-centered" role="document">
                    <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title" id="exampleModalLongTitle">${entry.title}</br>(${entry.date.slice(0,10)})</br>${entry.rating}/5</h5>
                        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                        </button>
                    </div>
                    <div class="modal-body">
                        ${entry.entry}</br></br>Today I am grateful for ${entry.grateful}
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                        <button type="button" class="btn btn-danger" onclick="deleteEntry()">Delete</button>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>`;
            html += htmlSegment;
        });

        let loadedEntries = document.querySelector('.loadedEntries');
        loadedEntries.innerHTML = html;
    }

    renderEntries();

# What is the plan for next week?

The project needs to be done this week so the last thing I need to figure out is how to delete the post. That is something I am struggling with and plan to get help with this week. I have it set up to how I think it should work but I get an error when I click on the delete button. My server code looks like this:

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

And my .js code looks like this:

    function deleteEntry() {
        return fetch('/entries/:id', {
            method: 'DELETE',
        }).then(response => response.json())
        .catch(error => {
            console.error('There has been a problem with your fetch operation:', error);
        });
    }

# What roadblocks did I encounter?

The roadblocks this week were just trying to figure out how to delete my posts. I plan to figure that out early this week.
