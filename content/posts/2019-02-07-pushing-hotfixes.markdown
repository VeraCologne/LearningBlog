---
layout: post
title:  "The One where I Push Some Hotfixes"
date:   2019-02-07 18:13:47 +0100
tags: 
- tools
---

Today was exciting! It started with a production deploy and running a script to add some data that had previously been gathered by a different application but is actually need in our application and belongs to one of our bounded contexts. The commits weren't big (and not mine, I think) and the script wasn't either and had been tested by one of our seniors on staging, so it wasn't really a big deal, but it felt cool to do something.

I did it with my coworker sitting next to me which was good because I had (again) forgotten how to use git flow for releasing. We actually only use it for easy merging and bumping versions because we develop mostly trunk based. And I learned that you can't just run a task on Heroku that needs a file path as an input because the file is just not there in the built application. Copying the script into the shell worked, though. And so far it looks like the script did what it was supposed to do.

After that we located a problem with an event URI to one of our other applications and since another team was waiting for this to be fixed and a user was waiting to use the application, we decided this should be fixed immediately. We didn't know where the bug was actually coming from though. I could reproduce it on staging, but it *worked on my machine*. When I got to this realisation, no one from my team was around to help me figure out where the hell it was coming from. Someone from another team heard me moaning and suggested that it was probably something with the database if it works for me but not on staging. This helped me figure out that the problem was that we are creating IDs differently than what they are when we consume events from other apps. That meant that both in my local database and in the tests everything looked fine.

There was still no one around and I could not really figure out what the supposed behaviour was: Do we want to save the UUID as the ID in our model and enrich it when publishing events or do we want to store the whole UUID and publish what is inside our model? I decided that the best choice for action at that point was to go with what's inside our staging and production database and fix the events accordingly. When my coworker came back for a few minutes between meetings, I quickly showed this to him and he said it was ok to push this to production which I did (on my own this time).

I'm a bit proud of myself. If someone had been around to help me, I would have asked for help early because of the fact that this had to be done rather quickly. I got to a point where I had no idea how to proceed several times and still continued looking in other places until I figured out what the problem was and how to fix it quickly.

I actually finished pushing this fix while carrying my laptop to one of our meeting rooms to do my session on stress management and mindfulness again, this time for our *Learning Hour*. Again we had a great conversation on the importance of mindfulness and I got some great input for my project of spreading information and resources about mindfulness in our company. Good day. 
