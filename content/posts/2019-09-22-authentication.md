---
title: "The One with Authentication"
date: 2019-09-22T17:35:53+02:00
tags:
- studitemps
- tools
- software craft
---

My project now has users who can login via Google. And only logged in users can see (only their own) learnings and add new ones.

I mostly followed Stephen Grider's [Elixir/Phoenix Bootcamp](https://www.udemy.com/the-complete-elixir-and-phoenix-bootcamp-and-tutorial/) course on Udemy. I had done this course before and remembered a bit about how the authentication was set up there, so I only needed to peek at his code every once in a while to make it work in my project.

Google's Developer Console is weird. I always get lost when trying to add a new OAuth client. And there are input fields where you have to first hit enter and then the save button, that's just weird. But aside from that, everything worked like a charm. His app structure and models are a bit different from mine so when it came to associating learnings with users, I had to think for a moment, but with a quick look at Ecto's documentation, that was no problem either.

I think my project is now in a stage where I could maybe deploy it somewhere? Oooh. And then I need to finally start refactoring. My Learnings module is a hot mess.