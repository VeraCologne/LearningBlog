---
title: "The One with My New Project"
date: 2019-09-13T18:35:53+02:00
tags:
- studitemps
- learning
- software craft
---

I started my new learning project today. And I'm already done with my MVP. Woohoo!

I explained my idea to Sascha yesterday and asked if he could help me with its implementation, along with Andreas from my former team, and he said yes. And then I pitched it to my boss and he like the idea, so I wanted to get started right away.

I think I have only vaguely mentioned what I wanted to do on here, so I'm going get into a bit more detail now. I want to build a Software Craft Learning Platform for Studitemps Software Engineers. So far, I have these ideas:

- a website that lists learning categories and topics with resources
- a way to track what a user is learning, based on the topics
- a way to analyse past learnings visually
- a suggestion feature for things to learn based on past activity
- a platform for people to offer their expertise in different topics
- maybe some gamification behind the expertise feature (that was actually my boss's idea)

Since I mainly wanted the tracking thing, that's what I started with. I have 3 models: Categories, Topics that belong to a category and Learnings that belong to a topic and a user, and have a description and a date. Learnings can be added by submitting a string with "Topic: Description".

Categories and Topics will not really change much, there is no need for them to be edited from the user interface, so I only needed to write a migration, define a schema and added some getter methods. The Category module actually has only one `get_name_by_id/1` function because I only need it to list all the learnings with their topics and the topics' categories. My Learning module does a bit much right now, with getting the correct topic from the user input (while allowing some shorthands), adding the current date to the changeset and persisting everything. But now is not the time for refactoring.

I was a bit confused about how to set up the data for Categories and Topics. So far, I had only worked with user-generated data with some additional constants inside the code itself, not with database objects that need to be there in order for things to work. But I got help, I have seeds now. If anything changes later on, it will be edited from some command line interface.

And as always, I struggled a bit with HTML, CSS, forms and things like that. But the Bootstrap website helped, along with an [HMTL to slim converter](https://html2slim.herokuapp.com/) and some peeking into my old team's projects. And after about half a day, I was done: I can add a new learning, as long as I reference an existing topic (and not if I don't, no crap in my database!) and I can list my learnings.

![Software Craft Learnings Table](/images/posts/2019-09-13-learning-table.png)

It does not look pretty but it's okay for now. I also have a list of all Topics/Categories as a starting page, but that is really just a plain old list and too ugly to show.

Now I need to think about what to do next. The whole platform thing will come last because I'm mostly interested in tracking/analysing what I learn. But do I add authentication and user management now so I can deploy it and let others play around with it? Or do I start with visualisations? Or jump into the suggestion feature (which needs even more data to be useful than visualisations)? I'll think about it.

