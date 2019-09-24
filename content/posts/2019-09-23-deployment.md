---
title: "The One with a Deployment"
date: 2019-09-23T17:35:53+02:00
tags:
- studitemps
- tools
- software craft
---

I have deployed my application to Heroku! I started setting up my project on Codeship and Heroku yesterday, but it did not really work. Since I couldn't figure out the Codeship error, I decided to manually push my project to Heroku for now. Which didn't work either.

I tried following Phoenix's tutorial on [Deploying to Heroku](https://hexdocs.pm/phoenix/heroku.html) but when I tried pushing, I got an error that the app could not be compiled because Heroku could not find the `prod.secret.exs` in its build folder. Yeah well if nothing has been built, where should this be? I asked my coworker and he told me not to use the secrets file but just add its content as variables in Heroku. And then I had missed some database configuration as well, so I just copied that from one of our old projects. And then it worked, hah!

There was my application, live on the interwebs. I seeded it with the Categories and Topics I had defined and then I could add Learnings. Something still seems to be wrong with signing up though, because one of my coworkers could log in and one could not. Something for tomorrow, I guess. Oh and refactoring. Maybe.