---
title: "The One with a Complicated Process Model"
date: 2019-05-14T13:33:53+02:00
tags: 
- studitemps
- architecture
- people
---

We have one application where the one main action is currently not usable by its users because we didn't anticipated that number of things calculated would increase as quickly as it did and currently, the synchronous process would time out at some point when triggered from the user interface. This action is now triggered by us from a command line interface and only after running some checks for common errors. 

This is a time-consuming process for us and needs a lot of communication between us and the users who are in another department and have a very different way of working than we have. Both parties want this changed. So this will be our main story[^1] for this sprint.

Instead of a synchronous process it will now become a managed process. When the user triggers the action, a process manager is started, it then publishes its own progress by listening to events and once the last event is done, it triggers the service that produces the output that the users need. 

We tried to model this on a big whiteboard. And it got complicated:
![Process Model](/images/posts/2019-05-14-model.jpg)

I lost track of the discussion several times. I tried to ask questions to get back into the modelling a few times, but ultimately decided it's not useful. We have decided to be very strict about pairing this sprint, so if the 2 senior backend devs understand their model, I might be able to learn it while implementing? My team mates weren't happy with that. 

Another *people problem* we have: I think I tend to ask for validation too much. I often get a reply telling me to decide for myself. Which is useful for learning, I guess, but difficult for me emotionally sometimes. Today it was the other way around: I was asked if I wanted to go through the process again in order for me to understand it better. I decided that this time-consuming action was not valuable enough for me, so I said no. The coworker who asked didn't like that answer. And he probably knows better and I would really learn from it, I just can't see the real benefit because of my lack of experience. But still, it's a bit hard to tell when I am supposed to decide for myself and when I should ask for advice instead of deciding. We'll work on that, I guess.

[^1]: While typing this, I am asking myself if that really is a user story. Because the functionality exists. The users come to us to tell us they need the output of the action and we trigger it and tell them they can now see the output. On the other hand, it gets a lot easier for them to do what they have to do (which is just one step in a bigger process) if they don't have to rely on us being available.